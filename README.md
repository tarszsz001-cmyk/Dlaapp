# DLA Saving Coop — ต้นแบบแอป (Capacitor)

ต้นแบบที่กดได้ 5 หน้า: หน้าแรก, บัญชี, บริการทั้งหมด (ค้นหาได้), สวัสดิการ, โปรไฟล์/ตั้งค่า
ปุ่มที่ยังไม่มีหน้าจริงจะเปิดแผ่นข้อความ "ต้นแบบ" ไม่ได้เชื่อมระบบจริง (ล็อกอิน ยอดเงิน โอนเงิน)

เนื้อหาทั้งหมดอยู่ในไฟล์เดียว: `www/index.html`

## วิธี A: ให้ GitHub สร้าง APK ให้ (ไม่ต้องลง Android Studio)
1. สร้าง repo ใหม่บน GitHub แล้วอัปโหลดทุกไฟล์ในโฟลเดอร์นี้ (รวมโฟลเดอร์ `.github`)
2. ไปที่แท็บ **Actions** > **Build debug APK** > **Run workflow**
3. รอประมาณ 5-8 นาที เปิดงานที่เสร็จแล้ว ดาวน์โหลด `dla-proto-apk` จากหัวข้อ Artifacts
4. แตกไฟล์ zip จะได้ `app-debug.apk` ส่งเข้ามือถือ Android แล้วติดตั้ง (ต้องอนุญาตติดตั้งจากแหล่งที่ไม่รู้จัก)

## วิธี B: Build ในเครื่อง
ต้องมี Node.js 18+, JDK 17 และ Android Studio (หรือ Android SDK)
```
npm install
npx cap add android
npx cap sync android
cd android && ./gradlew assembleDebug
```
ไฟล์อยู่ที่ `android/app/build/outputs/apk/debug/app-debug.apk`
หรือใช้ `npx cap open android` เพื่อเปิดใน Android Studio แล้วกด Run

## แก้ดีไซน์แล้วอัปเดตแอป
แก้ `www/index.html` แล้วรัน `npx cap sync android` จากนั้น build ใหม่

หมายเหตุ: ฟอนต์ IBM Plex Sans Thai โหลดจากอินเทอร์เน็ต ถ้าออฟไลน์จะใช้ฟอนต์ไทยของเครื่องแทน
