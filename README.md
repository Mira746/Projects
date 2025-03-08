Title:
Digital Baby Dose Reminder with Stopwatch and Alarm Functions.
Problem Statement:
To design and develop a digital electronics-based baby dose reminder system.
This system should include a stopwatch for tracking time intervals, an alarm to
remind users of medication times, and a timekeeping module that operates as
a digital watch. The reminder system must be user-friendly, allow manual
control of the alarm, and reset functionality for accurate dose tracking.
Theory:
The baby dose reminder system utilizes digital electronics components
such as counters, clock dividers, and comparators to achieve accurate
timekeeping and interval tracking. A 1 Hz clock pulse, created from a
higher frequency using a clock divider, is used to update time values. By
using separate modules for timekeeping, alarm, and stopwatch, the
system allows flexible functionality. Control logic and flip-flops are
incorporated for mode switching and debouncing button inputs to ensure accurate user control.
Methodology:
➢ Block Diagram: The block diagram includes the following main blocks
• Clock Divider: Divides a high-frequency clock signal to 1 Hz for
timekeeping.
• Timekeeping Module: Tracks the current time in hours,
minutes, and seconds.
• Alarm Module: Allows users to set an alarm time and triggers a
signal when the set time matches the current time.
• Stopwatch Module: Independently tracks time intervals for use
as a stopwatch with start, stop, and reset capabilities.
• Display Driver: Controls a seven-segment display to show time
and stopwatch values.
• Control Logic and Debounce Circuits: Manage mode switching
(clock, alarm, stopwatch) and stabilize button inputs.
• Explanation: The clock divider generates a 1 Hz pulse used by
counters to increment time values. The alarm module
compares the current time with the alarm time, and if they
match, it triggers a signal. The stopwatch module has its own
counters to independently track time intervals. A multiplexer
and control logic select which data (clock, alarm, or stopwatch)
appears on the display.
Software:
The project is developed using Verilog HDL (Hardware Description Language)
for programming the digital logic components. A simulator like ModelSim or
Xilinx Vivado is used to test the logic.
Implementation:
• Clock Divider: A 50 MHz input clock is divided to produce a 1 Hz clock
pulse.
• Counters: Used for seconds, minutes, and hours in the timekeeping and
stopwatch modules.
• Alarm Module: Contains a comparator that matches current time with
the alarm time. When matched, it triggers the alarm.
• Stopwatch Module: Operates independently, with counters that are
started, stopped, or reset based on user input.
• Control Logic: Manages mode switching and enables user control
through buttons.
• Display Driver: Outputs time data to a seven-segment display.
Algorithm:
1. If reset is high, reset seconds, minutes, hours, stopwatch_seconds,
stopwatch_minutes, and alarm_triggered to 0.
2. If reset is high, also reset stopwatch_running to 0.
3. On each clock edge, if reset is low, increment seconds by 1.
4. If seconds reaches 59, reset seconds to 0 and increment minutes.
5. If minutes reaches 59, reset minutes to 0 and increment hours.
6. If hours reaches 23, reset hours to 0.
7. If start_stopwatch is high, set stopwatch_running to 1.
8. If stopwatch_running is high, increment stopwatch_seconds by 1
on each clock edge.
9. If stopwatch_seconds reaches 59, reset stopwatch_seconds to 0
and increment stopwatch_minutes.
10. If stopwatch_minutes reaches 59, reset stopwatch_minutes to 0.
11. If reset_alarm is high, reset alarm_triggered to 0 and reset the
stopwatch.
12. If set_alarm is high, check if hours equals alarm_hour and
minutes equals alarm_minute.
13. If hours and minutes match alarm_hour and alarm_minute, set
alarm_triggered to 1; otherwise, set it to 0.
