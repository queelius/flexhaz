# flexhaz 0.5.3

## Changes

Likelihood, score, Hessian and fitting now reject invalid/missing censoring
codes and non-numeric, negative or non-finite observation times. Previously,
unknown or missing event codes silently omitted observations from the
log-likelihood. The missing-column convention (all observations exact), logical
indicators, zero times, custom column names and empty-data behavior are retained.
Regression tests cover likelihood and both analytical derivative entry points.

The README now describes the package's hazard-function workflow and links to
the official survival and flexsurv documentation, replacing an inaccurate
feature-comparison table.

## Local validation

Ubuntu 24.04.3 LTS, R 4.3.3, x86_64 Linux, checked 2026-10-28.

The first R CMD check --as-cran completed with 0 errors, 0 warnings and 2 notes:

* Unable to verify current time.
* HTML validation skipped because 'tidy' is unavailable; math rendering
  validation skipped because the 'V8' package is unavailable.

Remote CRAN incoming and dependency checks passed. Tests, examples (including
--run-donttest), vignette rebuilds and the PDF manual passed. Full development
tests passed; measured line coverage was 99.26%. The development suite reports
30 pre-existing warnings from optimizer evaluations/diagnostics. Integration
checks passed for serieshaz fitting/interoperability and maskedhaz
fitting/cross-validation with the changed source packages loaded together.

The final source archive, including regenerated README/documentation and all
53 input-validation assertions, also passed --as-cran with 0 errors, 0 warnings
and the same 2 notes. This repeat set _R_CHECK_CRAN_INCOMING_REMOTE_=false
to avoid repeating the remote incoming checks that passed on the first build.

No new Windows or macOS checks have been performed for this patch.
