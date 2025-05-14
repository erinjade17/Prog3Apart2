# AgriEnergyConnect

AgriEnergyConnect Prototype – README Overview

AgriEnergyConnect is a prototype web application designed to facilitate connections between farmers and employees within an agricultural energy ecosystem. The platform enables farmers to manage product listings while allowing employees to oversee farmer data and available products. This README outlines the steps for setting up the development environment, building and running the application, and understanding its core functionalities and user roles.

Table of Contents

Setting Up the Development Environment • Prerequisites • Installation Steps
Building and Running the Prototype • Building the Application • Running the Application
System Functionalities and User Roles • Farmer Role • Employee Role • Public Access
Database Configuration
Logging
Contributing
License
Setting Up the Development Environment This section walks you through preparing your development setup to run the AgriEnergyConnect prototype. Prerequisites Ensure the following software is installed: • Operating System: Windows, macOS, or Linux • .NET SDK: Version 7.0 or newer (Download from .NET) • IDE Options: o Visual Studio 2022 or later (Recommended for Windows/macOS) Download Visual Studio Include the ASP.NET and web development workload during installation. o Visual Studio Code (Cross-platform) Download VS Code Install the C# extension from the marketplace. • SQL Server LocalDB (default DB option): Usually installed with Visual Studio. If you're using a different SQL Server instance, ensure it's set up and running. Installation Steps

Clone the Repository Use a Git client or terminal to clone the project:

git clone <repository_url>

cd <repository_directory>

Restore NuGet Packages The project depends on external NuGet packages. o Visual Studio: Open the .sln file. Packages should restore automatically. If not, use: o Update-Package -reinstall via Tools > NuGet Package Manager > Package Manager Console. o Visual Studio Code: Open the folder, then use the terminal (Ctrl+`` or Cmd+``): o dotnet restore

Database Setup o Connection String Open appsettings.json and locate the DefaultConnection under ConnectionStrings: o "ConnectionStrings": { "DefaultConnection": "Server=(localdb)\MSSQLLocalDB;Database=AgriEnergyConnectDB;Trusted_Connection=True;MultipleActiveResultSets=true" } Modify this string if you're connecting to a different SQL Server instance. o Apply Migrations Run these commands to generate and apply the database schema: o Add-Migration InitialCreate o Update-Database

Building and Running the Prototype This section explains how to compile and launch the application locally. Building the Application • Visual Studio: o Open the .sln file. o Go to Build > Build Solution or press Ctrl+Shift+B (Cmd+Shift+B on macOS). o Monitor the Output window for errors. • Visual Studio Code: o Open the project folder and launch the terminal. o Run: o dotnet build Running the Application • Visual Studio: o Select the startup project in Solution Explorer. o Press F5 or go to Debug > Start Debugging. o The app will open in your browser at a local address (e.g., https://localhost:xxxx). • Visual Studio Code: o In the terminal, navigate to the project directory and run: o dotnet run o The terminal will display the local server URL. Open it in your browser.

System Functionalities and User Roles AgriEnergyConnect supports role-based functionalities as outlined below. Farmer Role Logged-in users with the "Farmer" role can: • View My Products: Access a list of their submitted products via the "My Products" navigation link. • Add Product: Add new products (name, category, production date) using the "Add Product" link. Employee Role Users with the "Employee" role have the following capabilities: • View Farmers: See a complete list of registered farmers via the "View Farmers" link. • Add Farmer: Register new farmers with their name, email, phone number, and location. • Filter Products: Filter all listed products by category and/or production date range on the "Filter Products" page. Public Access Non-authenticated users can: • View the Home Page • Login with existing credentials • Register a new account as either a "Farmer" or "Employee"

Database Configuration The application uses Entity Framework Core for database access. • The connection string is configured in appsettings.json under ConnectionStrings > DefaultConnection. • The default setup uses SQL Server LocalDB, but you may replace it with any accessible SQL Server instance. • Database schema management is handled via EF Core Migrations: o InitialCreate sets up base tables (Farmers, Products). o Use Add-Migration and Update-Database for future schema changes.

Logging AgriEnergyConnect uses the built-in .NET logging framework. • Logging is currently configured for console and debug output during development. • Modify Program.cs to integrate additional logging providers (e.g., file, third-party services). • Logging examples are implemented in the AccountController (e.g., login/logout actions).

Contributing Interested in contributing? Follow these steps:

Fork the repository on GitHub.

Create a new branch for your feature or fix.

Implement your changes with appropriate documentation.

Submit a pull request with a clear description of your update.

License This project is intended for demonstration purposes only and does not currently have a designated license. For licensing inquiries, please contact the project developers.

Thank you for exploring the AgriEnergyConnect prototype!
