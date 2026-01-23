# Eterea Clientes Portal

Static site for sharing training documents with clients.

## Links

- **Production:** https://eterea-clientes.vercel.app
- **GitHub:** https://github.com/etereapalma/eterea-clientes

## Auto-deploy

Pushes to `main` trigger automatic Vercel deployment. No manual deploy needed.

```bash
git add . && git commit -m "update" && git push
```

## Structure

```
/Clientes
  vercel.json         ← Clean URLs config
  /{client-name}/
    index.html        ← Client portal (links to their documents)
    propuesta.html    ← Training proposal
    factura-*.html    ← Invoices
    rutina-*.html     ← Mesocycle routines
```

## URLs

| Client | Portal URL | Example Document |
|--------|------------|------------------|
| Oana | `/oana/` | `/oana/propuesta` |
| María | `/maria/` | `/maria/propuesta` |

## Add New Client

```bash
# 1. Create folder
mkdir oana   # use lowercase, no spaces

# 2. Copy template
cp oana/index.html nuevo-cliente/
cp oana/propuesta.html nuevo-cliente/  # if similar

# 3. Edit content
# - Update name in index.html title and heading
# - Customize propuesta.html content

# 4. Deploy (auto on push)
git add .
git commit -m "Add cliente: nombre"
git push

# 5. Share link
# https://eterea-clientes.vercel.app/nuevo-cliente/
```

## Add Document to Existing Client

```bash
# 1. Create file
touch oana/factura-enero-2026.html

# 2. Add content (copy style from propuesta.html)

# 3. Add link in oana/index.html:
# <a href="factura-enero-2026.html">🧾 Factura Enero 2026</a>

# 4. Push
git add . && git commit -m "Add factura enero for Oana" && git push
```

## Old Link Redirect

The original link `https://oana-rutina-propuesta.vercel.app` redirects to the new portal.
That project lives in `/Negocio/Rutinas Personalisadas/` (separate Vercel project).

## Tips

- Use lowercase folder names without spaces
- Keep file names descriptive: `rutina-mesociclo-1.html`
- The `cleanUrls` config means `/oana/propuesta` works (no .html needed)
- Commit messages help track what changed when
