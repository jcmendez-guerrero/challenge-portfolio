# 2 Technological Constraints

At the moment of the design of the solution the following constraints were considered:

1. System should run on current Jenkins Implementations
2. Code should be stored in GitHub and releases should be administrated and generated there.
3. Only automated users/app should be able directly update stable
4. Regression Tests includes Unit Test
5. Functional Tests have it’s own repository and pipeline
6. Regression Tests can’t be applied to date generation libraries at the moment due that the stacktrace should be unique and independent.
