# Prowler CLI Cheat Sheet

## General Commands

See what options are available for a given provider
```
prowler aws -h
```

List out all supported services in a provider
```
prowler aws --list-services
```

List checks by cloud provider and by service
```
prowler aws --list-checks -s s3
```

Run Prowler with default checks
```
prowler
```

Run a specific group of checks
```
prowler -g <group>
```

Run a specific check
```
prowler -c <check>
```

List available checks and groups
```
prowler -l
```

Specify output format
```
prowler -M json
```

Specify output file
```
prowler -o <output_file>
```

Filter results by a specific string
```
prowler -f "<string>"
```

Run a custom check
```
prowler -c <check_id>
```

Run a custom group of checks
```
prowler -g <group_name>
```

## Prowler with AWS

Specify an AWS region
```
prowler -r us-west-2
```

Run Prowler across all AWS accounts
```
prowler -A
```

## Prowler with Azure

## Prowler with Google Cloud

## Options and Help

```
prowler aws --help
prowler azure --help
prowler gcp --help
```