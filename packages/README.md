# Notes
- Had to copy over package from nixpkgs, could not get override to work correctly
- Should check if another way to get cargoHash other than needing to manually fetch
  it via script.  We should see a cargo failure if we sepcify the old cargohash for
  older version of the app?
  - A: looks like the cargohaah is available with the "copy" method, unlike the
    "override" method.  Also interstingly, the cargohash is different from the one I got via
    the script?
- Have to specify different `pname` to build correcctly. Else, it looked like it
  conflicts with old package name? (Why is this?)
- Have to re-patch file with my own code to remove duplicat reqwest package.
  v0.190.0 changed the cargo.lock file, so previous 0002 patch didn't work.
