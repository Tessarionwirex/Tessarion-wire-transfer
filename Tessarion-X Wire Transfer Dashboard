
---

🔐 Supabase Auth Handler (auth.js)

> 📁 src/auth.js



// src/auth.js
import { createClient } from '@supabase/supabase-js';

const supabase = createClient(
  process.env.REACT_APP_SUPABASE_URL,
  process.env.REACT_APP_SUPABASE_KEY
);

export async function signUp(email, password) {
  const { data, error } = await supabase.auth.signUp({ email, password });
  if (error) throw error;
  return data;
}

export async function signIn(email, password) {
  const { data, error } = await supabase.auth.signInWithPassword({ email, password });
  if (error) throw error;
  return data;
}

export async function signOut() {
  const { error } = await supabase.auth.signOut();
  if (error) throw error;
}

export async function getUserSession() {
  const { data, error } = await supabase.auth.getSession();
  if (error) throw error;
  return data.session;
}

export default supabase;


---

🔐 Usage in React UI (App.js)

import { signIn, signUp, signOut, getUserSession } from './auth';

async function handleLogin(email, password) {
  try {
    const session = await signIn(email, password);
    console.log('Logged in:', session);
  } catch (err) {
    alert('Login failed: ' + err.message);
  }
}

async function handleSignup(email, password) {
  try {
    const result = await signUp(email, password);
    alert('Signup successful! Check your email.');
  } catch (err) {
    alert('Signup failed: ' + err.message);
  }
}


---

✅ Final Setup

1. Enable Email/Password Auth in Supabase dashboard → Auth → Settings


2. Add .env.local:



REACT_APP_SUPABASE_URL=https://xyz.supabase.co
REACT_APP_SUPABASE_KEY=your-public-anon-key

3. Restart dev server or redeploy on Vercel



You now have full auth flow integrated with Supabase! 🚀


---

