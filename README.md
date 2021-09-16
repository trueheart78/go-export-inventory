# Go! Export Inventory!

Designed for use with AWS Lambda and a remote Postgresql database to export current inventory
levels.

![Taylor Swift - Money Bat][taylor]

## Setup

### AWS Lambda

#### Lambda Binary

[Download it from the releases tab][releases] and upload that to your AWS Lambda function. In the _Handler_
field on the upload page, change the value to `lambda_handler`.

#### Environment Vars

You need to set the following in your configuration for your environment. If they are not setup, the lambda
will not work correctly.

```
STORE_HASH                       # The unique store hash identifier on BigCommerce.
X_AUTH_TOKEN                     # The X-Auth-Token for the BigCommerce API.
POSTGRES_DATABASE_URL            # The URL for the Postgresql DB.
```

## Development

```
go get github.com/trueheart78/go-export-inventory
```

Structure should stay with the [Standard Go Project Layout][layout].

## Building the Binary

Run the `build/lambda.sh` script and check the `out/` directory for the archive to use. Make sure to set the
_Handler_ field in the AWS Lambda page to `lambda_handler` when uploading.

[layout]: https://github.com/golang-standards/project-layout
[releases]: https://github.com/trueheart78/go-export-inventory/releases
[taylor]: assets/taylor-swift-money-bat.gif
