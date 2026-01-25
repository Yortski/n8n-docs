# Workflows

Workflows are the core building block in n8n.

![Workflow Example](images/workflow-example.png)

## Nodes
Each workflow is made of **nodes**:
- Trigger nodes
- Action nodes
- Logic nodes

## Example workflow (Webhook → HTTP Request)

```json
{
  "nodes": [
    {
      "name": "Webhook",
      "type": "n8n-nodes-base.webhook"
    },
    {
      "name": "HTTP Request",
      "type": "n8n-nodes-base.httpRequest"
    }
  ]
}
```