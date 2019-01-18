# 6. Use the Elite2 API to access NOMIS data

Date: 2019-01-18

## Status

Accepted

## Context

Our main source of data on prisoners and prison staff is NOMIS. The
allocation tool currently uses the Custody API, as decided in [ADR 0006](https://github.com/ministryofjustice/offender-management-architecture-decisions/blob/master/decisions/0006-use-the-custody-api-to-access-nomis-data.md), to retrieve
data on both offenders and staff.

Initial use of the Custody API has raised some issues. Problems exist
with the locality of data, N+1 API requests, and data that is unavailable
through the currently published endpoints. These issues are intrinsic to
the current design of the Custody API, and it is unlikely that they will
be resolved or mitigated in the short to medium term.

The Elite2 API, a fork of the Custody API, is under more active development
and provides endpoints more focused on the need of clients. Most of the
endpoints available work on the caseload of the connecting client token,
but also support the provision of more specific parameters to handle
alternate needs.  Although we will not be authenticating with the token
of the eventual end user, enough flexibility exists for us to obtain the
data we require from Elite2.


## Decision

We will use the Elite2 API for access to the data we require from NOMIS.

We will work with the team in Sheffield on development of the Elite2 API to
add support for accessing the data we need, in the structure that we need it.

## Consequences

We will have to rework the existing code to use the new API.

We will need to spend several days of pairing with people from Sheffield
to be able to contribute effectively.

We will need ongoing support from the team in Sheffield to review pull requests
and deploy API changes for us.
