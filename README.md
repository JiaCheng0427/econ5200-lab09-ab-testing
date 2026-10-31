# Diagnosing Experimental Failures in A/B Testing

## Objective

In this lab, I learned how to find common problems in A/B testing and how to make the results more reliable.

## Methodology

- I checked and fixed three problems in the CUPED code to reduce variance.
- I used sample ratio mismatch (SRM) tests to check whether users were divided correctly between groups.
- I simulated a marketplace experiment to see how interference affects A/B testing results.
- I used Bayesian A/B testing to compare two variants and calculate the expected loss.
- I wrote a function to repeat the Bayesian test with more users.
- I ran a sequential testing simulation to see how checking p-values many times can increase false positives.

## Key Findings

- The corrected CUPED method reduced variance by 82.7%, with a standard error of 0.0641.
- In the marketplace experiment, the naive ATE was 0.1861, while the global ATE was 0.1428. The naive estimate was 23.3% higher.
- In the Bayesian test, P(B > A) was 0.8866, and the expected loss of choosing B was 0.000473. This was not enough to ship B.
- The permutation test gave a p-value of 0.2302, so I could not reject the null hypothesis.
- With four times as many users, P(B > A) increased to 0.9951, and the decision changed to shipping B.
- In the sequential testing simulation, the false positive rate was 32.4% when checking repeatedly without correction. It dropped to 1.9% with Bonferroni correction, compared with 5.3% for a single test at the end.

## Conclusion

This lab helped me understand that A/B testing results can be misleading if the experiment is not designed or analyzed carefully. I also learned that using the right methods and collecting more data can help make better decisions.
