# Architecture

Selected Android notifications → consent/source/pause filter → structured intake →
weekly policy → local inbox → operator review → optional owned UI adapter → exact receipt.

Kotlin owns native background intake, local persistence and policy execution. React
provides a bundled offline interface through an origin-scoped WebView bridge. The
browser sandbox uses a TypeScript engine checked against the same policy fixtures.

The reference scheduler has an actual form and persistent appointment store. Only
its own submission handler creates appointments. The adapter uses named controls,
checks target identity and values, sends one confirmation, then verifies all receipt
fields. Source fixture emission and demo reset are maintenance, not a booking API.

Before action, the attempt is durably reserved. Interruptions or uncertain results
require review and cannot silently retry. The reference store enforces idempotency
and overlapping-slot rejection.

The MVP retains up to 200 requests and 160 audit events. It is not a multi-user CRM.
Generic selected source apps can be opened by the operator; they do not automatically
acquire a booking adapter. A production integration needs separate authorization,
interface evidence and acceptance.
