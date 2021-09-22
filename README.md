# job-azure-publish-webapp
A sequence of steps/actions that logins to Azure (CLI) and pushes a webapp to an App Service.
After that, it runs a database migration script on it.

## Usage

### Usage example
```yaml
    steps:
      - uses: EasyDesk/job-azure-publish-webapp@v1
        with:
          azure-credentials: ${{ secrets.AZURE_CREDENTIALS }}
          app-name: ${{ env.AZURE_APP_SERVICE_NAME }}
          publish-dir: app
          slot-name: <slot-name>
          migrations-script: update-database.sql
          db-server-name: ${{ secrets.DB_SERVER_NAME }}
          db-connection-string: ${{ secrets.DB_CONNECTION_STRING }}
```
