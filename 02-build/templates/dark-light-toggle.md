# Dark/Light Toggle — Template reutilisable

Copier-coller dans n'importe quel projet Next.js + Tailwind.

## 1. Hook (state + auto-detection)

```tsx
const [isDark, setIsDark] = useState(true);

useEffect(() => {
  const h = new Date().getHours();
  setIsDark(h < 7 || h >= 19);
}, []);
```

## 2. Container (wrapper de page)

```tsx
<div className={`min-h-screen transition-colors duration-500 ${
  isDark ? "bg-[#0a0a0a] text-white" : "bg-white text-gray-900"
}`}>
```

## 3. Bouton toggle

```tsx
<button
  onClick={() => setIsDark(!isDark)}
  className={`flex h-8 w-8 items-center justify-center rounded-full transition-colors ${
    isDark
      ? "bg-white/10 hover:bg-white/20 text-yellow-300"
      : "bg-gray-100 hover:bg-gray-200 text-indigo-500"
  }`}
>
  {isDark ? (
    <svg className="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth={2}>
      <circle cx="12" cy="12" r="5" />
      <path strokeLinecap="round" d="M12 1v2m0 18v2M4.22 4.22l1.42 1.42m12.72 12.72l1.42 1.42M1 12h2m18 0h2M4.22 19.78l1.42-1.42M18.36 5.64l1.42-1.42" />
    </svg>
  ) : (
    <svg className="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth={2}>
      <path strokeLinecap="round" strokeLinejoin="round" d="M21.752 15.002A9.718 9.718 0 0118 15.75c-5.385 0-9.75-4.365-9.75-9.75 0-1.33.266-2.597.748-3.752A9.753 9.753 0 003 11.25C3 16.635 7.365 21 12.75 21a9.753 9.753 0 009.002-5.998z" />
    </svg>
  )}
</button>
```

## 4. Palette de classes utilitaires

Utiliser `isDark` partout avec ce pattern :

```
${isDark ? "DARK_VALUE" : "LIGHT_VALUE"}
```

| Element | Dark | Light |
|---|---|---|
| **Background page** | `bg-[#0a0a0a]` | `bg-white` |
| **Texte principal** | `text-white` | `text-gray-900` |
| **Texte secondaire** | `text-white/60` | `text-gray-500` |
| **Bordure** | `border-white/10` | `border-gray-200` |
| **Card background** | `bg-white/[0.03]` | `bg-gray-50` |
| **Card hover** | `bg-white/5` | `bg-gray-100` |
| **Nav backdrop** | `bg-[#0a0a0a]/90` | `bg-white/90` |
| **Badge/pill** | `bg-white/10` | `bg-gray-100` |

## 5. Composants courants

### Nav

```tsx
<nav className={`fixed top-0 left-0 right-0 z-50 border-b backdrop-blur-md transition-colors duration-500 ${
  isDark ? "border-white/10 bg-[#0a0a0a]/90" : "border-gray-200 bg-white/90"
}`}>
```

### Card

```tsx
<div className={`rounded-2xl border p-6 ${
  isDark ? "border-white/10 bg-white/[0.03]" : "border-gray-200 bg-gray-50"
}`}>
```

## 6. Version HTML pur (sans React)

```html
<style>
  :root { --bg: #fff; --text: #111; --border: #e5e7eb; --card: #f9fafb; }
  .dark { --bg: #0a0a0a; --text: #fff; --border: rgba(255,255,255,.1); --card: rgba(255,255,255,.03); }
  body { background: var(--bg); color: var(--text); transition: background .5s, color .5s; }
</style>
<script>
  const h = new Date().getHours();
  if (h < 7 || h >= 19) document.documentElement.classList.add('dark');
  function toggleDark() { document.documentElement.classList.toggle('dark'); }
</script>
<button onclick="toggleDark()">Toggle</button>
```

## 7. Checklist

- [ ] `"use client"` en haut du fichier (Next.js)
- [ ] `useState` + `useEffect` pour auto-detection
- [ ] `transition-colors duration-500` sur le container
- [ ] `backdrop-blur-md` sur la nav
- [ ] Passer `isDark` en prop aux sous-composants
- [ ] Bouton toggle dans la nav (coin droit)
