
---

## 🧠 Features

- 🏢 Supports 4 floors: A, B, C, D
- 🎛️ FSM-based design using `case` and `parameter` states
- ⬆️⬇️ Direction output (`dir`) to indicate up/down motion
- 🧪 Testbench to simulate real-time floor requests
- 🧼 Clean, synthesizable RTL following industry best practices

---

## 🧪 Testbench Overview (`tb/tb_elevator.v`)

This testbench verifies the functionality of the elevator FSM by simulating:

- **Clock Generator**: 10ns period (50 MHz)
- **Reset Pulse**: FSM resets to floor A
- **Floor Requests**: Inputs simulated in sequence → `B → D → A → C`
- **Monitoring**: `$monitor` used to track outputs in terminal
- **Simulation Delay**: Each request held for 200ns

📤 Run using ModelSim, Vivado, or Icarus Verilog with:

```bash
iverilog -o elevator_tb src/elevator.v tb/tb_elevator.v
vvp elevator_tb
