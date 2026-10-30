# Playbook 03: Edge Functions & Realtime Subscriptions

Use this playbook for background triggers, webhook handlers, and live WebSocket subscriptions.

---

## 1. Realtime Database Subscription in React

```tsx
'use client';

import { useEffect, useState } from 'react';
import { createBrowserClient } from '@supabase/ssr';

export function LiveActivityFeed() {
  const [items, setItems] = useState<any[]>([]);
  const supabase = createBrowserClient(
    process.env.NEXT_PUBLIC_SUPABASE_URL!,
    process.env.NEXT_PUBLIC_SUPABASE_ANON_KEY!
  );

  useEffect(() => {
    const channel = supabase
      .channel('realtime_activities')
      .on(
        'postgres_changes',
        { event: 'INSERT', schema: 'public', table: 'activities' },
        (payload) => {
          setItems((prev) => [payload.new, ...prev]);
        }
      )
      .subscribe();

    return () => {
      supabase.removeChannel(channel);
    };
  }, [supabase]);

  return <div>{/* Render real-time items */}</div>;
}
```
