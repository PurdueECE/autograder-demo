# Overview

This grader will collect all repos that match a set of filters, checkout the latest commit before a due date, and run a set of tests against the submission.

# Files

* `.github/workflows/`
  * `grader_test.yml` - Workflow to test grading process with assignment template code.
  * `grader_all.yml` - Callable workflow to collect all repos under an org that match filters, checkout the latest commit before a due date, run a set of tests using the [grader module](https://github.com/PurdueECE/autograde.py), and upload the results as a workflow artifact.
  * `grader_assmt_*.yml` - Calls `grader_all.yml` with inputs to grade a specific assignment.
* `assmt_*` - Demo assignments
  * All grading files including unit tests are in the `tests/` subfolder. The tool will discover Python (`unittests`)[https://docs.python.org/3/library/unittest.html] in this folder. See the [grader module](https://github.com/PurdueECE/autograde.py) for more details.
  * An optional `config.json` file in the `test/` folder can be used to assign weights, name grader runs (for filling in student names), and weight each test.
  * Assignment template code is located in the `template/` subfolder and used as a fallback if grading student code fails.