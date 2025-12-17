# NIAGADS Developer Notes

This fork & branch were created b/c of the dependency of the `hgvs` library on the `psycopg2` package which requires a full install of postgres server and client at the systems level.  This is not feasible for our working environment.

This is a temporary fix.  We've made the following modification to the `pyproject.toml` file:

1. replaced `psycopg2` with the precompiled `psycopg2-binary`
2. explicitly set the version to 1.5.5 so that `ga4gh.vrs[extras]` will be content with this modified package

Please monitor [biocommons/hgvs](https://github.com/biocommons/hgvs) to 1) keep fork/branch in sync with major revisions and 2) abandon this fork when they resolve this issue on their own (they are currently assessing a move to `asyncpg`).


