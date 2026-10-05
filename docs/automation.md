# Automation Design

## Principle

**Automate repetition, not learning.**

Ares automation is optional. The project no longer assumes that a permanent controller, dashboard, or full scenario engine must be built. Manual setup is acceptable while exercises are infrequent because understanding the underlying systems is part of the learning objective.

## ARES-CTRL threshold

Build ARES-CTRL only when repeated Ares usage creates enough operational friction to justify it. If built, it may validate scenario definitions, check isolation and capacity, start required guests, verify telemetry, collect evidence, and reset the range.

It must not automate away the security-engineering reasoning the exercise is intended to teach.

## Possible scenario contract

For repeated scenarios, a manifest may declare:

- scenario purpose and engineering question;
- required guests and networks;
- resource budget;
- preflight isolation and authorization checks;
- controlled test steps;
- expected telemetry/detections;
- cleanup and snapshot restoration;
- evidence requirements.

## Guardrails

- Dry-run for automated destructive or high-impact actions.
- Isolation validation before controlled offensive activity.
- Allowlisted modules rather than arbitrary dashboard commands.
- No production credentials or personal data.
- Failed reset/isolation verification blocks the next automated run.
- Automation must remain understandable and overridable by the operator.

## Future layout

```text
automation/
  api/          optional controller endpoints
  engine/       optional state machine/task runner
  providers/    virtualization and guest adapters
  schemas/      optional manifest/report validation
  tests/        safety-gate and dry-run tests
```

This structure is a future option, not a commitment to build a separate Ares software platform.
