# Module 0: Serverless Project

<!-- TODO: Add introduction. -->

## Serverless Framework Overview

<!-- TODO: Add Serverless framework overview. -->

## Create Serverless project

**Goal:** Create AWS Lambda handler code using `serverless create` command. Invoke function locally to confirm that it returns:

```json
{
    "statusCode": 200,
    "body": "{\"message\":\"Go Serverless v1.0! Your function executed successfully!\",\"input\":\"\"}"
}
```

<!-- TODO: Add info about handler result: API Gateway lambda-proxy etc. -->

<details>
<summary><b>HOW TO create serverless project</b></summary>

Create nodejs Serverless project using one of the default templates:
`serverless create --template aws-nodejs`

See more information about `serverless create` command on [CLI documentation](https://serverless.com/framework/docs/providers/aws/cli-reference/create/) page.
</details>

<details>
<summary><b>HOW TO invoke function locally</b></summary>

Run `invoke local` command:

`serverless invoke local --function hello`

See more information about `invoke local` command on [CLI documentation](https://serverless.com/framework/docs/providers/aws/cli-reference/invoke-local/) page.
</details>

Congratulations! You have successfully successfully created Serverless API project.

## Completion

You have successfully created Serverless project and tested handler locally. In the next [Deploy API](1_Deploy) module, you will learn more about API Gateway and deploy your first serverless API.