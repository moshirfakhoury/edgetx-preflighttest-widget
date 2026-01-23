Checkout my other widgets:

https://github.com/moshirfakhoury/edgetx-postflight-widget

https://github.com/moshirfakhoury/edgetx-flightdash-widget

https://github.com/moshirfakhoury/edgetx-images-widget

https://github.com/moshirfakhoury/edgetx-servicechecklist-widget

Widget Overview

This widget serves as a preflight check, providing a quick visual overview of your model’s status. It highlights issues such as low battery or weak signal between the transmitter and model. The widget evaluates up to five logical switches, allowing you to define your own preflight rules by assigning logical switches in the widget parameters.

How the Widget Works
- Optimized for use with the APP or Full Screen layout, with no trims or sliders for best visibility.
- Evaluates up to five logical switches using simple logic.
- Inactive logical switch: displays “PASS” in green.
- Active logical switch: displays flashing “FAIL” in red.
- The parameters/options menu allows selection of five logical switches. While all switches are accessible, this widget functions correctly only with logical switches.
- Each switch parameter includes a label, allowing you to name each row as desired (maximum 12 characters).
- Switch parameters that are not assigned will not appear in the widget; using all five is optional.
- If any row shows “FAIL”, the final status will display “CHECKS FAILED” in red, and a sound will be played.
- The included sound file is used by default. You must place it in: /SOUNDS/en/SYSTEM on your transmitter SD card.
- To use a custom sound, replace the file named pfcf.wav in the same folder. Your replacement file must also be named pfcf.wav.
- If all rows show “PASS”, the Final Status will display “CHECKS PASSED” in green, and no sound will be played.
- In the bottom-right corner of the widget, a counter displays the number of passes and failures.

Advanced Features (Optional)
GV9 – Previous Failure Indicator
- The widget can optionally track previous failures per row using Global Variable 9 (GV9).
- GV9 uses Flight Modes FM4–FM8, corresponding to widget rows 1–5.
- This feature is disabled by default.
- To enable failure history tracking, set: GV9 FM0 = 1024
When enabled:
- A row that previously failed but now passes will display “Previous Failure” in flashing red.
- This indicator remains visible for a short time (default: ~9 seconds) before automatically clearing.
- The indicator is not shown if the row is currently failing.
- If GV9 FM0 is any value other than 1024, this feature is completely disabled and GV9 is ignored.

GV8 – Advisory (Non-Critical) Checks
- The widget can optionally treat certain checks as Advisory instead of failures using Global Variable 8 (GV8).
- GV8 uses Flight Modes FM4–FM8, corresponding to widget rows 1–5.
- This feature is disabled by default.
- To enable advisory mode, set: GV8 FM0 = 1024
When enabled:
- If a logical switch is active and the corresponding GV8 FMx value is 1024, the row will display “ADVISORY” in yellow.
- Advisory rows do not cause a failure, do not trigger sounds, and do not change the final status.
- Advisory rows count as passed in the pass/fail counter.
- This allows you to define checks that are informative but not flight-critical.
- If GV8 FM0 is any value other than 1024, advisory mode is disabled and all active logical switches are treated as failures.

Advanced Features Indicator (ADV / ADV+)
- When advanced features are enabled, a small indicator appears in the top-right corner next to the widget title:
- ADV (yellow): One advanced feature is enabled (either GV8 or GV9).
- ADV+ (green): Both advanced features (GV8 and GV9) are enabled.
- No indicator is shown if neither feature is enabled.
- This provides a quick, non-intrusive visual confirmation that advanced logic is active.

Widget Limitations
- Maximum of five rows due to screen size and EdgeTX’s 10-parameter limit.
- Combined logical switches can be used to evaluate more conditions or telemetry values.
- Logical switches that depend on telemetry will display “PASS” when the model is off; non-telemetry switches evaluate correctly.
- The background color is set to black by default to ensure visibility regardless of transmitter theme.
- To change this, edit the Lua script and comment out the following line: lcd.drawFilledRectangle(z.x, z.y, z.w, z.h, COLOR_BLACK)

<img width="517" height="288" alt="image" src="https://github.com/user-attachments/assets/b58028d2-9669-42b6-af71-2fb19dd5197b" />

<img width="513" height="292" alt="image" src="https://github.com/user-attachments/assets/a2a776a0-b8c2-4f7e-982e-90f56e6e2377" />

<img width="513" height="297" alt="image" src="https://github.com/user-attachments/assets/27f97378-cd40-4371-8d72-2b997c20340f" />

<img width="502" height="297" alt="image" src="https://github.com/user-attachments/assets/92e38805-5afa-41b3-bd47-1eaacf3f8716" />



