# Quick self-check — DevSecOps and the SDLC

Five short questions to check you understood the README. Try to
answer each one in your own words before looking at the answers at
the bottom. There are no trick questions — if you read Sections 1
to 7, you can answer all of these.

## The questions

**1.** A team runs a security scan once, right before release, and
fixes whatever it finds. Is that DevSecOps? Why or why not?

**2.** What is the difference between SAST and DAST, and why would a
team want both instead of just one?

**3.** A pipeline blocks every release because a scanner flags a
low-risk issue in a library the team does not even use in a risky
way. What is the problem here, and what should the team change?

**4.** Name one security job for each of these three stages: Plan,
Build, and Monitor. (One each is enough.)

**5.** "Shift-left" is often explained as "do security earlier".
What is missing from that short explanation — what does shift-left
*not* mean?

## Spot the mistake

Read this short scenario and find what is wrong with it:

> A small team stores its database password in the code so the app
> can connect while testing. They plan to move it to a secrets
> manager "later, when we have time". The code is in a private
> repository, so they figure it is safe for now.

There are two problems here, not one. The first is the password
itself. The second is the assumption about the repository: private
today does not mean private forever — repositories get shared with
contractors, access changes, and mistakes happen. The fix is also
twofold: move the secret out of the code now, and add secrets
scanning to the pipeline so the next one gets caught automatically.

## Answers

**1.** No. That is the old way — security as a final gate. DevSecOps
means security checks run at every stage, from planning onwards,
so problems are found when they are cheap to fix.

**2.** SAST reads the code without running it and flags risky
patterns (like a hardcoded password). DAST probes the *running*
application from the outside, like an attacker would. SAST cannot
see how the running system behaves, and DAST cannot see the code
itself — so each catches things the other misses.

**3.** The scan is blocking on findings that are not actually
serious, which teaches the team to route around the pipeline.
Block releases only for high-severity findings, put the rest on a
fix list with deadlines, and tune the scanner's rules.

**4.** Any reasonable answers count. For example: Plan — threat
modelling, or writing down security requirements. Build —
dependency scanning, or signing the build. Monitor — logging and
alerting, or having a practised incident response plan.

**5.** Shift-left does not mean doing *all* security early and then
forgetting about it — some things can only be checked on a running
system. And it does not mean making developers do the security
team's job with no help; the security team still builds the tools
and handles the hard cases.
