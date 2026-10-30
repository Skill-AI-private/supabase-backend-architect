# Playbook 02: Next.js SSR Auth & Cookie Setup (`@supabase/ssr`)

Use this playbook for integrating Supabase into Next.js App Router projects.

---

## 1. Installation

```bash
npm install @supabase/supabase-js @supabase/ssr
```

---

## 2. Server Component Client (`utils/supabase/server.ts`)

```ts
import { createServerClient } from '@supabase/ssr';
import { cookies } from 'next/headers';

export async function createClient() {
  const cookieStore = await cookies();

  return createServerClient(
    process.env.NEXT_PUBLIC_SUPABASE_URL!,
    process.env.NEXT_PUBLIC_SUPABASE_ANON_KEY!,
    {
      cookies: {
        getAll() {
          return cookieStore.getAll();
        },
        setAll(cookiesToSet) {
          try {
            cookiesToSet.forEach(({ name, value, options }) =>
              cookieStore.set(name, value, options)
            );
          } catch {
            // The `setAll` method was called from a Server Component.
            // This can be ignored if you have middleware refreshing user sessions.
          }
        },
      },
    }
  );
}
```
