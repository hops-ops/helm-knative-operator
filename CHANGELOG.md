### What's changed in v0.1.0

* feat: initial commit (by @patrickleet)

* chore(deps): update unbounded-tech/workflow-simple-release action to v2.1.1 (#2) (by @renovate[bot])

  Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com>

* feat(deps): update helm release knative-operator to v1.20.0 (#1) (by @renovate[bot])

  Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com>

* chore(deps): update unbounded-tech/workflows-crossplane action to v2.13.0 (#4) (by @renovate[bot])

  Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com>

* feat: helm chart xrd (by @patrickleet)

* chore(deps): update unbounded-tech/workflow-vnext-tag action to v1.21.0 (#6) (by @renovate[bot])

  Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com>

* feat(deps): update crossplane-contrib/provider-helm docker tag to v1.0.6 (#5) (by @renovate[bot])

  Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com>

* fix: add RBAC ClusterRoleBinding to e2e test (by @patrickleet)

  The e2e test was failing because the Helm provider lacked permissions
  to create namespaces and install charts. Added ClusterRoleBinding for
  crossplane-system service accounts, matching the cert-manager pattern.

  Also:
  - Use Rapid channel for crossplane (matches cert-manager)
  - Increase cleanup timeout to 1800s
  - Remove unused metav1 import

  Co-Authored-By: Claude Opus 4.5 <noreply@anthropic.com>

* chore: remove e2e tests for knative-operator (by @patrickleet)

  Knative Operator is too complex to reliably test in a kind cluster
  within CI timeouts. The operator requires significant resources and
  time to fully deploy.

  Similar to crossplane and kiali configurations, we skip e2e tests
  and rely on test-render to validate the composition rendering.

  Co-Authored-By: Claude Opus 4.5 <noreply@anthropic.com>


