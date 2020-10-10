# How to use

You could modify `serverless.yml` - `service` value to your favorite name.

---

Firstly, you need to install serverless framework.

```bash
$ npm install -g serverless
```

And you need to config aws credentials, please follow the aws [document](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-profiles.html).

Install layer plugin

```bash
$ sls plugin install -n serverless-ruby-layer
```

And deploy to aws

```bash
$ sls deploy
```

After deployed, you will see some outputs, copy the layers arn to your lambda layers, or you could find the arn in you AWS Lambda Layers list.

In your lambda project, you could config the `serverless.yml` use this layer like this

```yml
functions:
  my_own_function:
    handler: handler.call
    layers:
      - arn:aws:lambda:ap-northeast-1:xxxxxxx:layer:serverless-service-name-xxx:1
```

Deploy your lambda

```base
$ serverless deploy
```

And test `PG.library_version`

Voila~
