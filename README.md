# Minimalist Docusaurus Application

This is a minimalist Docusaurus application configured for both local development and Cloud Foundry deployment.

## Prerequisites

- Node.js 20.x
- npm 10.x
- Cloud Foundry CLI (for deployment)

## Local Development

1. Install dependencies:
   ```bash
   npm install
   ```

2. Start the development server:
   ```bash
   npm start
   ```

   This will start a local development server at http://localhost:3000.

3. Build for production:
   ```bash
   npm run build
   ```

4. Serve the production build locally:
   ```bash
   npm run serve
   ```

## Cloud Foundry Deployment

1. Login to your Cloud Foundry instance:
   ```bash
   cf login -a <your-cf-api-endpoint>
   ```

2. Deploy the application:
   ```bash
   cf push
   ```

   The application will be deployed using the configuration in `manifest.yml`.

## Configuration

- The application is configured to use the Node.js buildpack on Cloud Foundry
- Production deployment uses the `serve` command which binds to the port provided by Cloud Foundry
- Static assets are built during the `postinstall` script execution

## Environment Variables

- `PORT`: Automatically set by Cloud Foundry
- `NODE_ENV`: Set to 'production' in Cloud Foundry

## Additional Information

- The application uses TypeScript for enhanced type safety
- Built with Docusaurus 3.7.0
- Configured for optimal performance on Cloud Foundry
