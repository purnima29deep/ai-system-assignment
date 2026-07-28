# Part 2: Debugging Process

## Scenario

The AI pipeline experiences:

1 - Timeout errors
2 - Malformed JSON responses
3 - Silent incorrect outputs

## Step 1: Reproduce the Issue

Run the same request multiple times.

Check whether the failure is deterministic or intermittent.

## Step 2: Check Logs

Review:

1 - Application logs
2 - API logs
3 - Error stack traces
4 - Request IDs

## Step 3: Measure Latency

Identify which agent takes the longest time.

Example:

1- Input

2- Planner Agent

3 - Retriever

4 - Generator

5 - Validator

Record execution time for every stage.

## Step 4: Validate Output

Verify JSON schema after every agent.

Reject malformed outputs immediately.

## Step 5: Compare Expected vs Actual

Create test cases.

Example:

Expected:

{
    "status":"success"
}

Actual:

{
status:success
}

Problem:

Invalid JSON formatting.

## Step 6: Root Cause Analysis

Possible causes:

- Prompt ambiguity
- API timeout
- Missing retry logic
- Incorrect parser
- Corrupted cache

---

## Step 7: Fix

- Add retries with exponential backoff.
- Validate schema.
- Improve logging.
- Add timeout handling.
- Add unit tests.

## Tools Used

- Console Logs
- Postman
- Jest
- GitHub Actions