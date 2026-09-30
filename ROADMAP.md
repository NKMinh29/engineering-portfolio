# Roadmap — build evidence progressively

## Phase 1: document existing engineering work

- S32K144 Mini BCM: describe the current GPIO stage, reconstruct the build and record hardware evidence.
- CAN IDS research: inventory the exact source/build/logs before claiming reproducibility.
- CAN Log Workbench: run the synthetic sample, then write an adapter for a real log format.

## Phase 2: one complete application

Choose **ClubOps** for a concrete administrative workflow, or **Fleet Telemetry Console**
to connect web development to embedded and robotics work. Complete one end-to-end
flow, add tests for its meaningful failure cases, and record a demo before starting another app.

## Phase 3: automotive architecture

Write the three-ECU requirements and signal contract. Test pure application logic on
the host before replacing adapters with board-specific I/O. Distinguish an educational
layered design from a verified integration with a real AUTOSAR stack.

## Phase 4: selected extensions

Edge condition monitoring, LiDAR planning, drone replay, PCB bring-up, RTL verification,
secure updates and service-based gateways are independent directions. Select one at a time.

## Completion evidence

| Stage | Evidence |
|---|---|
| Design | Problem, interfaces, assumptions, acceptance criteria |
| Prototype | A complete demo using labeled synthetic or measured data |
| Tested demo | Repeatable commands, tests, results, known limitations |
| Hardware result | Board/configuration, raw logs, measurements and recovery procedure |

Avoid turning unmeasured targets into README results. Keep contributions, source provenance,
model/data limitations and test environments explicit.
