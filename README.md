# EK Outdoor CAD Platform

Outdoor-focused React/Vite CAD-style MVP for GitHub and Vercel.

## Default login
- Login: `EKADMIN`
- Password: `123456`

The password-change feature stores a SHA-256 hash in the current browser's localStorage. This is suitable only for an MVP/demo and is not secure server-side authentication.

## Features
- Upload 2D plan image
- Scale, unit and snap settings
- Drag real-image accessories; no cube placeholders
- Custom accessory image, name and dimensions
- AutoCAD-style layers, dimensions and annotations
- Textured-plane 3D view, VR-style preview
- Safe JSON plugin manifest registry
- GLB and OBJ export
- Deployment debugging for initializing, cloning, installing, building and deploying

## Local validation
```bash
npm install
npm run build
npm run preview
```

## Vercel
- Framework: Vite
- Build command: `npm run build`
- Output directory: `dist`
- Root directory: blank

See `docs/DEPLOYMENT-TROUBLESHOOTING.md`.
