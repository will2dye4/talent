# Talent Search

This project explores the implications of the talent search strategy used by a hypothetical
tech giant's engineering teams. The strategy can be summarized as follows:

> Only hire people who are better than 50% of those already in the role.

Effectively, this strategy creates a simple rule that must be followed in order to execute
the strategy successfully (referred to as "the rule" below):

> A new hire's talent rating must be in the 50th percentile (or higher) of existing
> employees' talent ratings.

This Jupyter notebook implements a simulation of this hiring strategy that obeys the rule, until
it is no longer possible to hire anyone else while still following the rule. The simulation
makes the following assumptions:

* In this hypothetical scenario, talent is the sole criterion that determines if a candidate is
  suitable for a role. Talent is modeled as a simple scalar value, and a candidate with a
  talent score above some threshold (as determined by the rule) is suitable to be hired.
* Talent is normally distributed among the population with a mean of 0.5 and a standard deviation
  of 0.15. (This roughly puts the range of talent scores between 0 and 1.)
* At time t = 0, when this hiring strategy is implemented, there is some existing set of employees
  already in the role. (Otherwise, it is impossible to know if new candidates are more or less
  talented than "those already in the role," which is necessary in order to follow the rule.)
  Further, we assume that at time t = 0, talent is normally distributed among the existing employees
  with the same mean and standard deviation as the population of candidates (as described above).
* There are an infinite number of roles to fill, i.e., the only limit to the hiring process is
  when no more candidates can be hired while still following the rule.
* When filling a role, candidates are hired randomly from the set of suitable candidates (as
  described above). In other words, any candidate with a talent score above the threshold dictated
  by the rule is equally likely to be hired.