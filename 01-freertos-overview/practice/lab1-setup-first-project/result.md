## คำถามทบทวน

1. ไฟล์ใดบ้างที่จำเป็นสำหรับโปรเจกต์ ESP-IDF ขั้นต่ำ?
- ans CMakeLists.txt ระบุ source และ component ของโปรเจกต์ ไฟล์ source เช่น main.c หรือ main.cpp ที่มี app_main()

2. ความแตกต่างระหว่าง `hello_esp32.bin` และ `hello_esp32.elf` คืออะไร?
- ans .elf เป็น executable พร้อม debug info ใช้สำหรับ debugging .bin เป็น binary สำหรับ flash ลง ESP32 รันจริง.

3. คำสั่ง `idf.py set-target` ทำอะไร?
- ans กำหนดเป้าหมายฮาร์ดแวร์ ESP32/ESP32-S2/ESP32-C3 ให้โปรเจกต์ ปรับ toolchain, linker script และ configuration ให้ตรงกับบอร์ด.

4. โฟลเดอร์ `build/` มีไฟล์อะไรบ้าง?
- ans มีไฟล์ object, .elf, .bin, map, log และ intermediate จากการ build ใช้สำหรับ flash และ debug, ไม่ควรแก้ไขโดยตรง.

5. การใช้ `vTaskDelay()` แทน `delay()` มีความสำคัญอย่างไร?
- ans vTaskDelay() yield CPU ให้ task อื่น ทำให้ multitasking ราบรื่น delay() block CPU ทั้งหมด ทำให้ task อื่นไม่สามารถรัน.
