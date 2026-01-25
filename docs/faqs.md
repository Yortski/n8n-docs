# n8n FAQs

## What is n8n?
n8n is an open-source workflow automation tool that allows you to connect different apps and services to automate tasks without writing code. Workflows are created using nodes that represent triggers, actions, or data transformations.

## What are nodes in n8n?
Nodes are the building blocks of workflows. Each node performs a specific task such as receiving data, processing it, or sending it to another service. Common node types include triggers, actions, function nodes, and app integrations.

## How do I start a workflow?
Workflows start with a **trigger node**, which can be something like a webhook, a scheduled event (Cron), or a new email in Gmail. Once the trigger fires, the workflow executes the connected nodes in order.

## How do nodes connect to each other?
Nodes are connected **from output to input**. A node can have multiple outputs and multiple nodes can feed into a single node. The workflow executes in the order defined by these connections.

## How do I add credentials to a node?
Some nodes require authentication to access external services. To add credentials:
- Open the node.
- Click **“Credentials”**.
- Select existing credentials or create new ones.
- Enter the required information (API key, OAuth token, username/password, etc.).
- Save and test the connection.

## Can I manipulate data inside a workflow?
Yes, using **function nodes** or **Set nodes**. Function nodes allow you to write JavaScript for custom data processing. Set nodes let you define or modify fields in your workflow data without coding.

## How do I test a workflow?
You can test workflows in two ways:
- **Execute Node** – runs a single node for testing.
- **Execute Workflow** – runs the full workflow from the trigger to the last node. Testing ensures that each step behaves as expected before activation.

## How do I activate a workflow?
After creating and testing a workflow, click **Activate** to enable it. Activated workflows run automatically whenever the trigger conditions are met.

## How can I debug a workflow?
- Use the **Execution Data** panel to inspect inputs and outputs of each node.  
- Check the **Error Trigger Node** if a workflow fails.  
- Add **Function nodes** or **Set nodes** temporarily to log data for inspection.

## Can workflows run in parallel?
Yes, n8n can execute multiple branches in parallel if a node has multiple outputs. However, some nodes like function nodes process data sequentially, so plan accordingly.

## How do I handle errors in workflows?
- Use **Error Workflow** to capture errors globally.  
- Use the **Continue on Fail** option on nodes to allow the workflow to continue even if a node fails.  
- Add **IF nodes** to create conditional logic to handle failures.

## Can I schedule workflows?
Yes, using the **Cron node**, you can schedule workflows to run at specific times, intervals, or even specific days of the week. This allows fully automated recurring tasks.

## Can I trigger workflows via HTTP?
Yes, the **Webhook node** allows workflows to start when they receive an HTTP request. This is useful for connecting web applications or external services that support webhooks.

## How do I share workflows?
- Export workflows as JSON files.  
- Import JSON files into another n8n instance.  
- Share credentials separately; they are not included in exports for security reasons.

## How do I keep workflows organized?
- Use **Folders** to group related workflows.  
- Use clear node naming and comments within nodes to document logic.  
- Break complex workflows into multiple smaller workflows that trigger each other.

## What are some best practices for building workflows?
- Keep workflows modular; break complex logic into smaller nodes.  
- Use function or set nodes to simplify data before sending it to other apps.  
- Test nodes individually before running the full workflow.  
- Reuse credentials whenever possible to avoid duplication.  
- Document workflow logic with comments and node names for future maintenance.
