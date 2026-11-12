# PhoneStore — Render deployment package

This package contains the published ASP.NET Core application and a Dockerfile for Render.

## Deploy
1. Upload the contents of this folder to a new GitHub repository (not the ZIP file itself).
2. In Render, choose **New → Web Service**, connect the repository, and select **Docker** as the runtime.
3. Choose the **Free** instance plan and create the service.
4. Wait for the deployment to finish. Render will provide an `https://...onrender.com` URL.

The application targets .NET 10. The Dockerfile listens on port 10000.

## Important database note
This published bundle does not include a SQLite database file. If the app creates/uses a local SQLite database, Render's free filesystem is temporary: data can be lost when the service restarts, sleeps, or redeploys. Test the app after deployment and do not enter real/private data. A persistent database setup may be needed for durable records.

## Free-tier behavior
Render free web services can sleep after 15 minutes without traffic and may take about a minute to wake up.
