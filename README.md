# Project Setup Working Document 

## Project Overview
This project aims to develop an e-commerce website builder with blogging functionality for small businesses. It leverages React for the front-end and Flask for the back-end, with payment integration using Stripe.

## Architecture
1. **Presentation Layer (Front-End)**: React app (hosted on Azure Static).
2. **Business Logic Layer (Back-End)**: Flask hosted on Azure Functions.
3. **Data Layer**: MS SQL 
4. **Static Assets**: Azure Blob Storage.
5. **Content Delivery**: Azure CDN.
6. **Content Management**: Strapi hosted on Azure App Service.

## Cost Estimates
- **Azure Static Web Apps**: Free tier
- **Azure Functions**: Free tier
- **Azure Cosmos DB**: Free tier
- **Azure Blob Storage**: Free tier
- **Azure App Service**: Free tier

Total estimated monthly cost: **$0 - $20**

## Useful Links
- [Azure Pricing Calculator](https://azure.microsoft.com/en-us/pricing/calculator/)
- [Docker Documentation](https://docs.docker.com/)
- [Stripe API Reference](https://stripe.com/docs/api)
- [Strapi Documentation](https://strapi.io/documentation/)
