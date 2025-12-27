# Weight-Based Sorting System

## Overview
This project is an industrial automation system designed to sort products based on their weight.
Products are classified into different categories according to predefined weight thresholds.

---

## System Operation
Products move along conveyor belts and are transferred to a weighing conveyor.
When a product is detected by the weighing sensor, all conveyors stop to ensure accurate measurement.
After a predefined delay, the weighing process is considered complete and the conveyors resume operation.

Once the products reach the sorting conveyor, they are separated based on their weight and directed to the appropriate conveyor.

When products enter the left or right conveyor belts and are detected by sensors, they are counted individually.
At the end of each conveyor line, products are transferred into crates located on another conveyor system.
When the predefined product count for a crate is reached, the system continues operation with a new crate.

The number of products passing through the left and right conveyors is displayed on separate displays.

---

## Control and Safety
The conveyor belt speeds can be adjusted by the operator.
If a predefined maximum conveyor speed is exceeded, products cannot be transferred properly.
In this case, the system generates an alarm and stops automatically.

A **Stop button** is implemented to bring the system to a complete stop, requiring the operator to press the Start button again to resume operation.

An **Emergency Stop button** is also implemented; after the emergency stop condition is cleared, the system can continue operation from its previous state.

A **Reset button** is used to reset all counters to zero, allowing the system to restart the process from the beginning.

---

## Software Architecture
The PLC program is designed using a structured programming approach.

A single **Function Block (FB)** is used for both the left and right conveyor diverters.
Instead of writing separate logic for each conveyor, the control logic is implemented once and parameterized for reuse.
This approach makes the program easier to maintain and reuse.

Additionally, a **time-delay interrupt** is implemented.
The interrupt is triggered when the conveyor speed exceeds the defined limit, ensuring a fast and reliable system response.

---

## Technologies Used
- PLC programming (TIA Portal)
- Factory I/O (Simulation)

![Factory I/O Image](https://github.com/MelihCimen482/weight-based-product-sorting-system/blob/7116ac789d2c526dae7cb555c1d17925a9624f51/images/Project_1.2.png)
![TIA_PORTAL_ALARM_STATUS](https://github.com/MelihCimen482/weight-based-product-sorting-system/blob/1bb302bef63b4c44febc7e5ba2cf141cd2de24a5/images/Project_1.4.png)
