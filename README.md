# TrueYield

A DeFi yield aggregator that helps you maximize returns across multiple protocols. TrueYield is a fork of [Harvest Finance](https://harvest.finance) with significantly lower fees — **10% performance fee** compared to Harvest's 30%.

## Features

- Auto-compounding yield strategies across DeFi protocols
- Support for Ethereum and Polygon networks
- WalletConnect, Coinbase Wallet, and Ledger integration
- 10% performance fee (vs Harvest's 30%)

## Getting Started

### Prerequisites

- Node.js: v`20.x` (LTS)
- Yarn: v`1.22.x`

### Local Setup

1. Clone the repository with submodules:

   ```bash
   git clone --recurse-submodules https://github.com/agorevski/harvest.git
   cd harvest
   ```

2. Copy `.env.example` to `.env` and fill in the required values:

   ```bash
   cp .env.example .env
   ```

   See [`.env.example`](.env.example) for all available environment variables.

3. Install dependencies:

   ```bash
   yarn install
   ```

4. Start the development server:

   ```bash
   yarn start
   ```

   The app will be available at [http://localhost:8080](http://localhost:8080).

### Updating Submodules

```bash
git submodule update --init
git submodule update --remote --merge
```

## Available Scripts

| Command | Description |
|---------|-------------|
| `yarn start` | Start the production server (`node server.js` on port 8080) |
| `yarn build` | Build the app for production using `react-app-rewired` |
| `yarn test` | Run the test suite |
| `yarn eslint` | Lint the codebase |
| `yarn eslint:fix` | Auto-fix lint issues |

## Deployment

TrueYield is deployed to **Azure App Service** via GitHub Actions.

- **URL:** [trueyield.azurewebsites.net](https://trueyield.azurewebsites.net)
- **Trigger:** Pushes to `main` branch or manual dispatch
- **Workflow:** [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml)

### Setup

The deployment requires the `AZURE_WEBAPP_PUBLISH_PROFILE` secret to be configured in the repository:

1. In the Azure Portal, navigate to **App Service → trueyield → Deployment Center → Manage publish profile**
2. Download the publish profile XML file
3. In GitHub, go to **Settings → Secrets and variables → Actions**
4. Create a new secret named `AZURE_WEBAPP_PUBLISH_PROFILE` with the contents of the downloaded XML file

## License

This project is licensed under a private license. For more information see [`LICENSE.md`](LICENSE.md).
