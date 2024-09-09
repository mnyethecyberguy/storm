# Prowler CLI Cheat Sheet

## General Commands

See what options are available for a given provider
```
prowler <provider> --help
```

Show Prowler version
```
prowler <provider> --version
```

## Services

List out all supported services in a provider
```
prowler <provider> --list-services
```

Scan specific services only
```
prowler <provider> --services <service>
```

Exclude specific services
```
prowler <provider> --excluded-services <service>
```

## Checks

List available checks for a provider
```
prowler <provider> --list-checks
```

List checks by cloud provider and by service
```
prowler <provider> --list-checks -s s3
```

Execute specific check(s)
```
prowler <provider> --checks <check>
```

Exclude specific check(s)
```
prowler <provider> --excluded-checks <check>
```

## Categories

List the available categories in the provider
```
prowler <provider> --list-categories
```

Execute specific category(s):
```
prowler  <provider> --categories
```

## Miscellaneous

Filter findings by status
```
prowler <provider> --status [PASS, FAIL, MANUAL]
```

Hide the Prowler banner
```
prowler <provider> --no-banner
```

## Prowler with AWS

Specify an AWS region
```
prowler aws -r us-west-2
```

Scan specific services only
```
prowler aws --services s3 ec2
```

Execute specific check(s)
```
prowler aws --checks s3_bucket_public_access
```

## Prowler with Azure

## Prowler with Google Cloud

## Options and Help

```
prowler aws --help
prowler azure --help
prowler gcp --help
```

## Additional References
https://hub.docker.com/r/toniblyx/prowler/tags