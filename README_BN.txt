WorkMate Offline — মোবাইল থেকে APK তৈরির প্যাকেজ

এতে আছে:
- www/index.html: প্রাথমিক অ্যাপ UI ও prototype feature
- Capacitor config ও Android project তৈরির package.json
- .github/workflows/build-apk.yml: GitHub Actions-এ APK build করার workflow

শুধু Android ফোন থেকে APK তৈরির ধাপ:
1. এই ZIP ফাইলটি ফোনে ডাউনলোড করে Extract করুন।
2. Chrome-এ github.com খুলে সাইন ইন/অ্যাকাউন্ট তৈরি করুন।
3. New repository তৈরি করুন, নাম দিন workmate-offline; Public বা Private যেকোনোটি বেছে নিন।
4. Extract করা ফোল্ডারের ভেতরের ফাইলগুলো repository-র root-এ আপলোড করুন। গুরুত্বপূর্ণ: .github ফোল্ডার এবং তার ভেতরের workflows/build-apk.yml ফাইলটিও আপলোড হতে হবে।
5. সব ফাইল main branch-এ commit করুন।
6. Repository-র Actions ট্যাবে যান। “Build WorkMate Offline APK” workflow খুলে “Run workflow” চাপুন (অথবা main-এ ফাইল commit করার পর স্বয়ংক্রিয়ভাবে শুরু হতে দিন)।
7. Build শেষ হলে workflow run খুলুন, নিচে Artifacts থেকে WorkMate-Offline-APK ডাউনলোড করুন।
8. ZIP artifact Extract করে app-debug.apk-তে ট্যাপ করুন। Android জিজ্ঞাসা করলে Chrome/Files-কে “Install unknown apps” অনুমতি দিন, তারপর Install করুন।

গুরুত্বপূর্ণ সীমাবদ্ধতা ও নিরাপত্তা:
- এটি একটি প্রাথমিক prototype-কে Android wrapper-এ প্যাকেজ করে। এই build নিজে থেকে উৎপাদন-মানের নিরাপত্তা নিশ্চিত করে না।
- PIN সাধারণ localStorage-এ থাকে; ডেটাবেস এনক্রিপ্টেড নয়। গোপন কোম্পানি ডেটা রাখবেন না যতক্ষণ না নিরাপদ স্টোরেজ যোগ ও পরীক্ষা করা হয়।
- ব্রাউজার-ভিত্তিক localStorage-এ থাকা পুরোনো ডেটা APK-তে স্বয়ংক্রিয়ভাবে আসবে না।
- অ্যাপ uninstall বা app data clear করলে ডেটা হারাতে পারেন; নিয়মিত Backup নিন।
- GitHub Actions-এর build সফল হওয়া পর্যন্ত APK তৈরি হয়েছে বলে ধরা যাবে না।
- Debug APK ব্যক্তিগত পরীক্ষার জন্য; Play Store-এ প্রকাশের জন্য signed release build লাগবে।
