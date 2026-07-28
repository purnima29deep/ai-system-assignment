

# AI System Assignment

Hi!

This repository contains my solution for the AI System Assignment.

I tried to solve all three parts in a simple way and also understand why we use these concepts in real projects.

---

## Tech Stack

- Node.js
- Express.js
- GitHub Actions

---

## Project Structure

```
backend/
docs/
.github/workflows/
README.md
```

- backend -> contains the Express server.
- docs -> contains the explanation for token optimization and debugging.
- .github/workflows -> contains GitHub Actions workflow files.
- README -> project explanation.

---

# Part 1 - Token Optimization

In this part I focused on reducing the number of input tokens without affecting the quality of the response.

### Optimization 1 - Context Summarization

Instead of sending the complete conversation every time, older messages can be summarized and only the latest conversation is sent to the model.

This reduces the token usage a lot while keeping almost the same context.

### Optimization 2 - Retrieval (RAG)

Instead of sending the complete document, only the relevant information is retrieved and passed to the model.

This reduces cost as well as response time.

### Token Comparison

Before - 100,000 Tokens
After - 28,000 Tokens

This gives around 72% reduction in token usage.

---

# Part 2 - Debugging

If the pipeline starts failing, I would not directly start changing code.

My approach would be:

1 - First reproduce the issue.
2 - Check logs and error messages.
3 - Find which step is actually failing.
4 - Check if there is any timeout.
5 - Validate the JSON output.
6 - Fix the issue and test again.

This helps in finding the exact root cause instead of guessing.

# Part 3 - CI/CD (continous integration/ continous deployment )

I created a basic GitHub Actions workflow.

The workflow:

1 - Installs dependencies
2 - Runs tests
3 - Runs lint checks

Deployment happens automatically when code is pushed to the main branch.

## Secrets

API keys should never be hardcoded in the source code.

They should be stored using GitHub Secrets and accessed securely during deployment.

## Rollback Plan

If deployment breaks production, I would:

1. Stop the deployment.
2. Roll back to the previous stable version.
3. Check logs to identify the issue.
4. Fix the problem in staging.
5. Deploy again after testing.

---

## What I Learned

While working on this assignment I learned more about:

 * Token optimization
 * AI pipeline debugging
 * GitHub Actions
 * CI/CD basics
 *  Deployment strategy

Thank you for reviewing my submission.