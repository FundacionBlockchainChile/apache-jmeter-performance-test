# JMeter Performance Testing with GitHub Actions

This repository contains automated performance tests using Apache JMeter, executed through GitHub Actions.

## Test Scenario

The test plan performs the following:
- Calls the JSONPlaceholder API endpoint `/users`
- Simulates 50 concurrent users
- Ramps up over 10 seconds
- Executes 5 loops per thread
- Collects performance metrics including:
  - Average Response Time
  - Error Rate
  - Throughput

## Structure

- `test-plan/` - Contains JMeter test plan files
- `.github/workflows/` - GitHub Actions workflow definitions
- `reports/` - Test execution reports (generated during run)

## Running the Tests

The tests are automatically executed through GitHub Actions on:
- Push to main branch
- Manual workflow dispatch

## Viewing Results

After each test run:
1. Go to the Actions tab in GitHub
2. Select the completed workflow run
3. Download the artifacts to view detailed reports

## Local Execution (Optional)

If you want to run the tests locally:

```bash
# Install JMeter first, then:
jmeter -n -t test-plan/users-test-plan.jmx -l results.jtl -e -o reports
``` 