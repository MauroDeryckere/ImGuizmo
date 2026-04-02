Vendored `ImGuizmo` source for Atrium Alloy.

Origin:
- Upstream: https://github.com/CedricGuillemet/ImGuizmo

Why vendored:
- The project currently needs a local picking-tolerance patch for gizmo usability.
- Keeping the modified source in-repo is safer than patching generated `_deps` content.

Current local change:
- Added public hit-tolerance fields to `ImGuizmo::Style`.
- Replaced hard-coded picking tolerances in `ImGuizmo.cpp` with those style fields.
- Atrium configures the desired tolerances from project code instead of relying on private constants.

Intended follow-up:
- Move this exact change set into a proper fork or upstream PR.
- Once a fork or upstream commit exists, CMake can be switched back to a pinned external source.
