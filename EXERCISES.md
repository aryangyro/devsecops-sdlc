# DevSecOps Exercises

Hands-on exercises to go with the guide in `README.md`. Each one takes
about 15–20 minutes. Work through them in order — they build on each
other.

## 1. Map your own pipeline

Draw the pipeline for a project you actually work on (a course project
counts). Mark each stage: plan, code, build, test, release, deploy,
operate. Then, for each stage, write down one security check that
*could* happen there. Compare your list with section 4 of the README —
which stages did you leave empty?

## 2. Shift-left a real bug

Take a security bug you have seen before (an SQL injection, a leaked
secret, a missing check). Write down, in one sentence each:

- When was it found?
- When *could* it have been found?
- What check would have caught it earlier, and at which stage?

If the answer to the second question is "a week earlier", that is the
whole point of shift-left.

## 3. Automate one thing, by hand first

Pick one check from your pipeline map — for example, "no secrets in
committed code". First do it manually: open your last five commits and
check them yourself. Then write down exactly what you checked, step by
step. That list of steps *is* the spec for automating it. Automation
is only useful when you know what the manual version looks like.

## 4. Spot the false sense of security

A team adds a security scanner to the pipeline and stops reviewing
code by hand. What could go wrong? Write down three things a scanner
typically misses (hint: business logic flaws, secrets in the wrong
place, and anything the scanner was never told to look for). Then
write down what should stay manual.

## 5. The "who owns this?" drill

Pick one security incident — real or made up, e.g. a dependency with a
known vulnerability is found in production. Write down who should do
each of these, and how fast:

- Decide whether it matters for this project
- Fix it or work around it
- Tell the users
- Make sure it does not happen again

If any step has no owner, that is a gap in the process, not a gap in
the tooling.

## 6. Start-small plan

Using section 9 of the README ("How to start small"), write a
one-page plan for adding security to a project that has none today.
Three rules: it must fit in one week, it must not need a new tool to
buy, and the first step must be something a single person can do
alone. If your plan needs a committee, it is too big — cut it down.
