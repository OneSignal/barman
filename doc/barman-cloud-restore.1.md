% BARMAN-CLOUD-RESTORE(1) Barman User manuals | Version 2.12
% 2ndQuadrant <http://www.2ndQuadrant.com>
% November 5, 2020

# NAME

barman-cloud-restore - Restore a PostgreSQL backup from the Cloud


# SYNOPSIS

barman-cloud-restore [*OPTIONS*] *SOURCE_URL* *SERVER_NAME* *BACKUP_ID* *RECOVERY_DIR*


# DESCRIPTION

This script can be used to download a backup previouslymade with
`barman-cloud-backup` command. Currently only AWS S3 is supported.
Tablespaces are restored in the original location.

This script and Barman are administration tools for disaster recovery
of PostgreSQL servers written in Python and maintained by 2ndQuadrant.


# POSITIONAL ARGUMENTS

SOURCE_URL
:    URL of the cloud source, such as a bucket in AWS S3.
     For example: `s3://BUCKET_NAME/path/to/folder` (where `BUCKET_NAME`
     is the bucket you have created in AWS).

SERVER_NAME
:    the name of the server as configured in Barman.

BACKUP_ID
:    the ID of the backup to restore

RECOVERY_DIR
:    the path to a local directory for recovery (used as PGDATA).

# OPTIONS

-h, --help
:    show a help message and exit

-V, --version
:    show program's version number and exit

-t, --test
: test connectivity to the cloud destination and exit

-P, --profile
: profile name (e.g. INI section in AWS credentials file)

-e ENCRYPT, --encrypt ENCRYPT
: enable server-side encryption with the given method for the transfer.
  Allowed methods: `AES256` and `aws:kms`.

--endpoint-url
: override the default S3 URL construction mechanism by specifying an endpoint.

# REFERENCES

For Boto:

* https://boto3.amazonaws.com/v1/documentation/api/latest/guide/configuration.html

For AWS:

* http://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-set-up.html
* http://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html.

# DEPENDENCIES

* boto3

# EXIT STATUS

0
:   Success

Not zero
:   Failure


# BUGS

Barman has been extensively tested, and is currently being used in several
production environments. However, we cannot exclude the presence of bugs.

Any bug can be reported via the Github issue tracker.

# RESOURCES

* Homepage: <http://www.pgbarman.org/>
* Documentation: <http://docs.pgbarman.org/>
* Professional support: <http://www.2ndQuadrant.com/>


# COPYING

Barman is the property of 2ndQuadrant Limited
and its code is distributed under GNU General Public License v3.

© Copyright EnterpriseDB UK Limited 2011-2021
