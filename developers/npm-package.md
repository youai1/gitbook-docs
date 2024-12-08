---
description: Integrate MindStudio's AI Workers into your Node.js projects.
---

# NPM Package

The [**MindStudio NPM Package**](https://www.npmjs.com/package/mindstudio) is your toolkit for integrating AI-powered workflows seamlessly into any application. This client library offers type-safe interfaces to help you execute MindStudio AI Workers with ease and confidence.

## **Quick Start**

### **1. Install the Package**

```json
npm install mindstudio
```

### **2. Get Your API Key**

* Go to [MindStudio Developer Settings](https://app.mindstudio.ai/workspace/settings/developer?page=api-keys)
* Create a new API key

### 3. Choose Your Usage Pattern

#### Option A: Type-Safe Usage (Recommended)

```jsx
**// Initialize the client
const client = new MindStudio(process.env.MINDSTUDIO_KEY);

// Execute a workflow
const { success, result } = await client.workers.myWorker.generateText({
  prompt: "Write a story about a space cat"
});

// Handle the response
if (success) {
  console.log(result);
}**
```

#### **Option B: Direct Usage**

```jsx
**import { MindStudio } from 'mindstudio';

const client = new MindStudio(process.env.MINDSTUDIO_KEY);
const { success, result } = await client.run({
  workerId: "your-worker-id",
  workflow: "generateText",
  variables: {
    prompt: "Write a story about a space cat"
  }
});**
```

***

## **Response Format**

All workflow executions return a consistent response type:

```jsx
interface WorkflowResponse<T> {
  success: boolean;
  result?: T;          // The workflow result when success is true
  error?: Error;       // Error details when success is false
  billingCost?: string // Execution cost in credits
}
```

***

## **CLI Commands**

### **`sync`**

Generate type definitions for type-safe usage:

```jsx
# With API key in environment
npx mindstudio sync

# With explicit API key
npx mindstudio sync --key your-api-key

# From existing config (CI environments)
npx mindstudio sync --offline
```

### **`test`**

Test a workflow from the command line:

```jsx
npx mindstudio test --worker myWorker --workflow generateText --input '{"prompt":"Hello"}'
```

### **`list`**

List available workers and workflows:

```jsx
# List from existing configuration
npx mindstudio list

# List from API (if no configuration exists)
npx mindstudio list --key your-api-key
```

***

## **Team Usage**

### **1. Project Owner:**

```jsx
**npx mindstudio sync
git add .mindstudio.json
git commit -m "Add MindStudio configuration"**
```

### **2. Team Members:**

```jsx
**npm install
npx mindstudio sync --offline**
```

### Optional: Add to `package.json` for automatic type generation:

```json
{
  "scripts": {
    "postinstall": "npx mindstudio sync --offline"
  }
}
```

***

## **Installation & Setup**

### **Environment Variables**

MindStudio requires an API key for authentication. You can provide it in several ways:

#### Option 1: In your shell

```json
export MINDSTUDIO_KEY=your-api-key
```

#### Option 2: In your .env file

```json
MINDSTUDIO_KEY=your-api-key
MINDSTUDIO_BASE_URL=https://custom-api-endpoint.com
```

#### Option 3: Pass directly to your CLI commands

```json
npx mindstudio sync --key your-api-k
```

#### For security best practices:

* Never commit API keys to version control
* Add `.env` to your `.gitignore`
* Use environment variables in CI/CD environments

### **TypeScript Configuration**

```tsx
{
  "compilerOptions": {
    "esModuleInterop": true,
    "resolveJsonModule": true
  }
}
```

***

## **Error Handling**

```tsx
// Workflow errors
const { success, result, error } = await client.workers.myWorker.generateText({
  prompt: "Hello"
});

if (!success) {
  console.error('Workflow failed:', error);
  return;
}

// Client errors
try {
  const client = new MindStudio('invalid-key');
} catch (error) {
  if (error instanceof MindStudioError) {
    console.error('Client error:', error.message);
  }
}
```

***

## **Common Issues**

#### **"Type-safe workers not available"**

Run `npx mindstudio sync` to generate type definitions

#### **"API key is required"**

Ensure `MINDSTUDIO_KEY` is set in your environment or passed to the constructor

#### **"Failed to load configuration"**

Run `npx mindstudio sync` to create initial configuration

***

## **Best Practices**

### **1. API Key Security**

* Store API keys in environment variables
* Use `.env` files only for local development
* Never commit API keys to version control
* Use secure environment variables in CI/CD

### **2. Type Safety**

* Use the type-safe pattern when possible
* Commit `.mindstudio.json` to version control
* Run `sync` after pulling changes

### 3. Error Handling

* Always check `success` before using `result`
* Implement proper error handling
* Use TypeScript for better type safety

***

#### **License**

MIT
