# Samples using Docker in a GitHub Actions workflow
This repository contains three (3) sample workflows that demonstrate using docker containers in your GitHub Actions workflow.

Workflow Name | File Name | Description
--- | --- | ---
Docker Action Example | .github/workflows/docker-action-example.yml | Runs a docker action
Service Container Example on Runner | .github/workflows/service-containers-on-runner.yml | Runs a job directly on the runner and leverages a service container
Service Container Example with Job Container | .github/workflows/service-containers-with-job-container.yml | Runs a job within a container and leverages a service container

### Workflow examples leveraging a service container

When you run this workflow, you should see the following output in the "Connect to Redis" step confirming you created the Redis client and added data:

```
Reply: OK
Reply: 1
Reply: 1
Reply: 1  
3 replies:
    0: octocat
    1: dinotocat
    2: robotocat
```


### client.js
This script creates a Redis client and populates the client with some placeholder data. The script then prints the values stored in the Redis client to the terminal. Your script can use any language you'd like, but this example uses Node.js and the redis npm module. For more information, see the [npm redis module](https://www.npmjs.com/package/redis).

You can modify client.js to include any Redis operations needed by your workflow. In this example, the script creates the Redis client instance, adds placeholder data, then retrieves the data.

The script creates a new Redis client using the createClient method, which accepts a host and port parameter. The script uses the REDIS_HOST and REDIS_PORT environment variables to set the client's IP address and port. If host and port are not defined, the default host is localhost and the default port is 6379.

The script uses the set and hset methods to populate the database with some keys, fields, and values. To confirm that the Redis client contains the data, the script prints the contents of the database to the console log.
