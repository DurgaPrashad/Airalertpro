# AirAlert Pro Frontend

This is the frontend for the AirAlert Pro application, built with React, Vite, and Tailwind CSS.

## Environment Variables

Create a `.env` file in this directory with the following variables:

```env
VITE_API_URL=https://your-backend-url.com
```

For local development, you can use:

```env
VITE_API_URL=http://localhost:5000
```

## Deployment to Vercel

1. Push your code to a GitHub repository
2. Create a new project on Vercel
3. Connect your repository
4. Set the following environment variables in Vercel:
   - `VITE_API_URL`: Your backend API URL
5. Deploy!

## Local Development

1. Install dependencies:
   ```bash
   npm install
   ```

2. Create a `.env` file with your backend URL

3. Run the development server:
   ```bash
   npm run dev
   ```

The app will be available at `http://localhost:5173`

## Building for Production

```bash
npm run build
```

The built files will be in the `dist` directory.
