# GitHub + Vercel deployment troubleshooting

## Required repository root
`src/`, `public/`, `.github/`, `index.html`, `package.json`, `package-lock.json`, `vercel.json`, `.nvmrc`.
Do not commit `node_modules`, `dist`, `.vercel`, `.env`, ZIP archives, large plan images, GLB or OBJ files.

## 1. Initializing
- Confirm the Vercel project exists and the GitHub integration is installed.
- Confirm Node.js 22 is selected or `.nvmrc` is present.
- If initialization fails before cloning, reconnect the Git provider and verify Vercel platform status.

## 2. Cloning
- GitHub App must have access to the exact repository.
- Production branch must exist and normally be `main`.
- Remove accidental Git submodules and `.gitmodules` when not required.
- Remove Git LFS dependencies for large images/models; store those outside the code repository.
- Confirm the repository was not deleted, transferred, renamed, or linked to an inaccessible organization.

## 3. Installing
- Commit both `package.json` and `package-lock.json`.
- Use Install Command `npm ci` or leave Vercel automatic detection enabled.
- Never upload `node_modules`.
- Locally reproduce with `npm ci`.

## 4. Building
- Framework Preset: Vite.
- Build Command: `npm run build`.
- Output Directory: `dist`.
- Root Directory: blank if `package.json` is at repository root.
- Reproduce with `npm run build`; fix the first error, not the final exit code.
- Linux is case-sensitive: `style.css` differs from `Style.css`.

## 5. Deploying
- `vercel.json` must be at repository root.
- If deploy succeeds but refresh returns 404, verify the SPA rewrite.
- If the page is blank, inspect browser Console and Network tabs.
- Old assets may be cached; open the latest deployment URL and promote it to Production.

## Verification
1. GitHub Actions `Validate build` is green.
2. Vercel Deployment status is Ready.
3. Login with `EKADMIN / 123456`.
4. Upload a plan image, drag an accessory, change its name, switch to 3D, and export GLB.
