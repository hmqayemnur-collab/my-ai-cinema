MY AI CINEMA — মোবাইল PWA স্টার্টার

এখন কী কাজ করে:
- বাংলা গল্প থেকে দৃশ্যভাগ ও photorealistic video prompt তৈরি
- প্রতিটি দৃশ্যে একই চরিত্র বজায় রাখার নির্দেশনা
- প্রম্পট কপি ও স্ক্রিপ্ট TXT ডাউনলোড
- Android browser-এর speechSynthesis দিয়ে বাংলা ভয়েস প্রিভিউ (ডিভাইসে বাংলা voice থাকতে হবে)
- 9:16 ভিডিও preview-তে HTTPS ভিডিও URL বসানো যায়
- PWA service worker আছে; HTTPS hosting-এ install করা যাবে

গুরুত্বপূর্ণ সীমাবদ্ধতা:
এই starter নিজে AI ভিডিও রেন্ডার করে না। বাস্তব ভিডিও তৈরির জন্য একটি video-generation provider-এর API এবং নিরাপদ backend দরকার। ফ্রি API-এর quota/availability পরিবর্তিত হয়। শুধু frontend-এ API key রাখবেন না।

ফ্রি static hosting:
1. GitHub-এ নতুন public repository তৈরি করুন।
2. ZIP extract করে সব ফাইল repository-তে upload করুন।
3. Settings > Pages > Deploy from a branch > main / root নির্বাচন করুন।
4. প্রকাশিত HTTPS URL Android Chrome-এ খুলুন।
5. Chrome menu > Add to Home screen / Install app নির্বাচন করুন।

AI video API যুক্ত করার পরামর্শ:
- Backend হিসেবে Cloudflare Worker / অন্য serverless backend ব্যবহার করা যায়, provider-এর বর্তমান free quota আগে যাচাই করুন।
- API key শুধু backend environment secret-এ রাখবেন।
- app.js থেকে backend-এর নিজের endpoint-এ request পাঠাবেন; provider key কখনো browser-এ পাঠাবেন না।
- API provider ও account-specific quota নিশ্চিত না করে কোনো generation-কে “free/unlimited” বলবেন না।

লোকাল টেস্ট:
কম্পিউটারে project folder থেকে একটি local web server চালান; file:// দিয়ে খুললে PWA/service worker ঠিকমতো কাজ নাও করতে পারে।
