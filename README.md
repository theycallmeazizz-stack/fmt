# Find My Tutor India — WebView Android App

Yeh ek WebView app hai jo aapki website **findmytutorindia.com** ko ek native
Android app ke roop me wrap karti hai.

**Features:**
- Poori website app ke andar khulti hai
- Back button se peeche jaata hai (exit nahi karta jab tak history khatam na ho)
- Pull-to-refresh (upar se kheech ke refresh)
- File upload support (forms me file/photo bhejne ke liye)
- Call / WhatsApp / Email / Maps jaise link automatically sahi app me khulte hain
- Internet na hone par offline page dikhata hai
- App icon aur loading progress bar

---

## ✅ Tarika 1: GitHub Actions se APK (kuch install karne ki zaroorat NAHI)

Yeh sabse aasaan tarika hai. Bas browser chahiye.

1. https://github.com par account banayein (free) aur ek **naya repository** banayein.
2. Is folder ki saari files us repo me upload kar dein
   (GitHub website par "Add file" > "Upload files" se drag-drop bhi kar sakte hain).
3. Upload hote hi build apne aap chalu ho jaayega.
   Repo me upar **"Actions"** tab kholein.
4. "Build APK" workflow run complete hone ka wait karein (~3-5 min, green tick aane tak).
5. Us run par click karein > niche **"Artifacts"** section me
   **`FindMyTutorIndia-debug-apk`** download karein.
6. ZIP ke andar **`app-debug.apk`** milega — wahi aapki app hai.

> Phone me install karte waqt "Unknown sources / Play Protect" warning aaye to
> "Install anyway" / "Allow" dabayein (yeh normal hai kyunki app abhi Play Store se nahi hai).

---

## 💻 Tarika 2: Android Studio se (apne computer par)

1. [Android Studio](https://developer.android.com/studio) install karein.
2. **Open** > yeh `FindMyTutorApp` folder select karein.
3. Gradle sync apne aap ho jaayega (pehli baar thoda time lega).
4. Menu: **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
5. APK yahan banega:
   `app/build/outputs/apk/debug/app-debug.apk`

---

## 🔧 Website ka URL badalna ho to

`app/src/main/java/com/findmytutor/india/MainActivity.java` file kholein,
upar ye do lines hain:

```java
private static final String HOME_URL = "https://findmytutorindia.com";
private static final String ALLOWED_HOST = "findmytutorindia.com";
```

In dono ko apni naye domain se badal dein.

## 🎨 App ka naam / icon

- Naam: `app/src/main/res/values/strings.xml`
- Icon: `app/src/main/res/mipmap-*/ic_launcher.png` (apni image se replace kar dein)

---

## 📱 Play Store par daalna ho to (baad me)

Yeh **debug APK** testing/sharing ke liye theek hai. Play Store ke liye
ek **signed release** banana padta hai (keystore se sign + `assembleRelease`).
Zaroorat ho to bata dena, woh setup bhi de dunga.
