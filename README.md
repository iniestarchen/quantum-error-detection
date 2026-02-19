# [[4,2,2]] Quantum Error Detection Code

> **Category**: error-correction &nbsp;|&nbsp; **Difficulty**: intermediate &nbsp;|&nbsp; **Qubits**: 4 &nbsp;|&nbsp; **Gates**: 4 &nbsp;|&nbsp; **Depth**: 4

The [[4,2,2]] code is the smallest quantum error detecting code. It encodes 2 logical qubits into 4 physical qubits and detects (but cannot correct) any single-qubit error. The logical |00_L⟩ = (|0000⟩+|1111⟩)/√2, equivalent to a 4-qubit GHZ state. Two stabilizer generators ⟨XXXX, ZZZZ⟩ define the code space. A single-qubit error maps the state out of the code space, detectable by measuring stabilizers.

## Expected Output

50% |0000⟩, 50% |1111⟩ (logical |00_L⟩)

## Circuit

The OpenQASM 2.0 circuit is in [`circuit.qasm`](./circuit.qasm).

```
OPENQASM 2.0;
include "qelib1.inc";
// [[4,2,2]] code: prepare logical |00_L> = (|0000> + |1111>) / sqrt(2)
qreg q[4];
creg c[4];
h q[0];
cx q[0],q[1];
cx q[0],q[2];
cx q[0],q[3];
measure q[0] -> c[0];
measure q[1] -> c[1];
measure q[2] -> c[2];
measure q[3] -> c[3];
```

## Tags

`error-detection` `css-code` `stabilizer` `fault-tolerant`

## References

- [Vaidman, Goldenberg, Wiesner (1996). Error Prevention Scheme with Four Particles. PRA 54(3), R1745](https://doi.org/10.1103/PhysRevA.54.R1745)

## License

MIT — part of the [OpenQC Algorithm Catalog](https://github.com/openqc-algorithms).
