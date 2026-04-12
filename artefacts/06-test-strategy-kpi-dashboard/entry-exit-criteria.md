# Entry / Exit Criteria

Per-phase gate criteria for the test lifecycle.

## Phase 1: Unit Test

### Entry Criteria
- [ ] Code complete and peer reviewed
- [ ] Unit test framework configured
- [ ] Test data available in DEV

### Exit Criteria
- [ ] All unit tests pass (0 failures)
- [ ] Code coverage ≥ 80%
- [ ] No Critical or High severity defects open
- [ ] Static analysis clean

## Phase 2: Integration Test

### Entry Criteria
- [ ] Unit test exit criteria met
- [ ] All interfaces deployed to SIT
- [ ] Integration test scenarios documented
- [ ] Test data loaded in SIT

### Exit Criteria
- [ ] All integration test scenarios pass
- [ ] All API contracts validated
- [ ] No Critical defects open
- [ ] ≤ 3 High defects open (with mitigation plan)

## Phase 3: SIT / Performance

### Entry Criteria
- [ ] Integration test exit criteria met
- [ ] End-to-end processes configured
- [ ] Performance test environment ready
- [ ] Load test scripts prepared

### Exit Criteria
- [ ] All SIT scenarios pass
- [ ] Performance benchmarks met (response time, throughput)
- [ ] No Critical defects open
- [ ] ≤ 5 High defects open (with mitigation plan)
- [ ] Stress test completed

## Phase 4: UAT

### Entry Criteria
- [ ] SIT exit criteria met
- [ ] UAT environment refreshed
- [ ] Business users trained
- [ ] UAT scenarios agreed

### Exit Criteria
- [ ] All UAT scenarios executed
- [ ] Business sign-off obtained
- [ ] No Critical or High defects open
- [ ] Medium defects have remediation plan
- [ ] Go-live readiness confirmed
