================================================================================
                    HSCianTV — Complete Platform Documentation
================================================================================

📱 অ্যাপের নাম: HSCianTV (অ্যাডমিন সেটিংস থেকে পরিবর্তনযোগ্য)
🌐 টাইপ: Progressive Web App (PWA) - মোবাইল ও ডেস্কটপ উভয়ে কাজ করে
📦 টেকনোলজি: React 18, TypeScript, Firebase, Tailwind CSS, Vite
🔗 Live URL: https://coursecast-quest.lovable.app
👨‍💻 Developer: Md Ridoan Mahmud Zisan
📅 Last Updated: March 2026

================================================================================
                              অ্যাপের সংক্ষিপ্ত বিবরণ
================================================================================

HSCianTV হলো একটি সম্পূর্ণ Online Course & Classroom Platform — যেটি YouTube-এর
মতো ভিডিও স্ট্রিমিং, কোর্স ম্যানেজমেন্ট, এক্সাম সিস্টেম, পেমেন্ট ভেরিফিকেশন,
ডিভাইস কন্ট্রোল সবকিছু সাপোর্ট করে।

================================================================================
                              প্রধান ফিচারসমূহ
================================================================================

✅ YouTube-এর মতো ভিডিও প্লেয়ার (Custom Controls, Speed 0.25x-2x, Seek ±10s)
✅ কোর্স ভিত্তিক ভিডিও অর্গানাইজেশন (Subject → Chapter → Video)
✅ MCQ এক্সাম সিস্টেম (অটো গ্রেডিং, টাইমার, সিকিউরিটি)
✅ 2-ডিভাইস লগইন লিমিট (পাইরেসি প্রোটেকশন)
✅ পেমেন্ট ভেরিফিকেশন সিস্টেম (স্ক্রিনশট + ট্রানজেকশন আইডি)
✅ সম্পূর্ণ Admin Panel (Users, Courses, Videos, Exams, Settings)
✅ PWA সাপোর্ট (Install as App)
✅ Dark/Light থিম
✅ মোবাইল-ফার্স্ট ডিজাইন
✅ AI চ্যাটবট (Floating Assistant)
✅ Data Export/Import (JSON)
✅ Content Protection (Copy/Select Disabled)

================================================================================
                              ইউজার প্যানেল
================================================================================

──── রেজিস্ট্রেশন ফ্লো ────
1. ইউজার রেজিস্ট্রেশন ফর্ম পূরণ করবে (নাম, ইমেইল, পাসওয়ার্ড)
2. কোর্স ড্রপডাউন থেকে কোর্স সিলেক্ট
3. পেমেন্ট মেথড দেখে টাকা পাঠাবে
4. Transaction ID ও Screenshot দিবে
5. রেজিস্ট্রেশনের পর status: pending হবে
6. Admin অ্যাপ্রুভ করলে কোর্স কন্টেন্ট দেখতে পারবে

──── ডিভাইস লগইন লজিক ────
- লগইন করলে deviceIds অ্যারেতে ডিভাইস যোগ হবে
- সর্বোচ্চ ২টি ডিভাইস
- ৩য় ডিভাইসে লগইন করলে আগের সব ডিভাইস ক্লিয়ার হবে
- GlobalSecurity কম্পোনেন্ট রিয়েল-টাইমে ডিভাইস চেক করে

──── Classroom (ক্লাসরুম) পেজ ────
- Subject Chips (হরাইজন্টাল স্ক্রলেবল ফিল্টার)
- Chapter Chips (সাবজেক্ট সিলেক্ট করলে দেখাবে)
- Video Grid (1/2/3 কলাম — মোবাইল/ট্যাবলেট/ডেস্কটপ)
- Thumbnail + Title

──── ভিডিও প্লেয়ার ────
- YouTube IFrame API ব্যবহার
- কাস্টম কন্ট্রোলস (Play/Pause, Seek ±10s, Speed, Fullscreen)
- মোবাইলে Double-tap Seek (বাম → -10s, ডান → +10s)
- Keyboard Shortcuts: Space/K (Play), ←/J (-10s), →/L (+10s), F (Fullscreen)
- Playback Speed: 1x → 1.25x → 1.5x → 1.75x → 2x
- Previous/Next Video (একই সাবজেক্ট)
- PDF ডাউনলোড বাটন
- More Videos সেকশনে Chapter ফিল্টার
- ডেস্কটপে: বামে ভিডিও, ডানে More Videos সাইডবার

──── এক্সাম সিস্টেম ────
- MCQ পরীক্ষা (Multiple Choice Questions)
- টাইমার — সময় শেষ হলে অটো সাবমিট
- ফলাফল দেখা — সঠিক/ভুল উত্তর হাইলাইট
- পাস/ফেইল স্ট্যাটাস
- এক্সাম সিকিউরিটি (ট্যাব সুইচ ডিটেকশন)

──── AI Assistant (ফ্লোটিং চ্যাটবট) ────
- কোর্স তথ্য জানানো
- পেমেন্ট তথ্য দেখানো
- এনরোলমেন্ট গাইড
- যোগাযোগ তথ্য
- WhatsApp Direct Message

──── প্রোফাইল পেজ ────
- নাম, ইমেইল, কোর্স তথ্য
- Enrolled Courses তালিকা
- Active Course সুইচ
- লগআউট বাটন

================================================================================
                              অ্যাডমিন প্যানেল
================================================================================

──── কিভাবে Admin হবেন? ────
1. Firebase Console → Firestore → users collection
2. আপনার user document-এ role: "admin" সেট করুন
3. status: "approved" সেট করুন

──── Dashboard ────
- Total Users, Pending Users, Total Courses, Total Videos, Total Exams
- Quick Action Cards (শর্টকাট বাটন)

──── User Management ────
- সকল ইউজার টেবিল (Name, Email, Course, Status, Date)
- কোর্স ভিত্তিক ফিল্টার
- Actions: Approve, Reject, Activate/Deactivate, Delete
- পেমেন্ট স্ক্রিনশট দেখার সুবিধা
- Search ফাংশন

──── Course Management ────
- কোর্স তৈরি/এডিট/ডিলিট
- সাবজেক্ট ও চ্যাপ্টার যোগ (nested structure)
- ইন্সট্রাক্টর যোগ (নাম, সাবজেক্ট, ছবি)
- ডিসকাশন গ্রুপ (Facebook, Telegram লিংক)
- রুটিন PDF URL
- All Materials লিংক
- Thumbnail, Price, Overview Points
- কোর্স অর্ডারিং (Up/Down arrows)

──── Video Management ────
- কোর্স → সাবজেক্ট → চ্যাপ্টার সিলেক্ট
- Video Title, YouTube URL, PDF URL, Thumbnail URL
- ভিডিও অর্ডারিং
- এডিট/ডিলিট
- Bulk upload সমর্থিত নয় (একটি একটি করে যোগ)

──── Exam Management ────
- MCQ এক্সাম তৈরি
- কোর্স ও সাবজেক্ট সিলেক্ট
- প্রশ্ন যোগ (4 অপশন, সঠিক উত্তর মার্ক)
- সময় সীমা সেট (মিনিটে)
- পাস মার্কস সেট
- Active/Inactive টগল

──── App Settings ────
- App Name ও Logo পরিবর্তন
- Social Media Links (Facebook, YouTube, WhatsApp, Telegram)
- Payment Methods (নাম + নম্বর, একাধিক যোগ করা যায়)
- Useful Links (যেকোনো কাস্টম লিংক)
- YouTube Upload Link, Google Drive Link (Admin shortcuts)

──── Data Export/Import ────
- Export: সম্পূর্ণ ডাটাবেস JSON ফাইলে ডাউনলোড
- Import: JSON ফাইল আপলোড করে ডাটা রিস্টোর
- Collections: users, courses, videos, enrollRequests, exams, examResults, settings
- ⚠️ Import করলে পুরানো ডেটা overwrite হবে

================================================================================
                        Firebase Database Structure
================================================================================

──── Collections Overview ────

Collection        | Document ID         | Description
users             | Firebase Auth UID   | ইউজার প্রোফাইল, ডিভাইস তথ্য
courses           | Auto ID            | কোর্স তথ্য, সাবজেক্ট, ইন্সট্রাক্টর
videos            | Auto ID            | ভিডিও তথ্য
enrollRequests    | Auto ID            | এনরোলমেন্ট রিকোয়েস্ট
exams             | Auto ID            | এক্সাম প্রশ্ন ও সেটিংস
examResults       | Auto ID            | এক্সাম ফলাফল
settings          | main_settings      | অ্যাপ সেটিংস

──── users Collection ────
{
  name: string,
  email: string,
  role: "student" | "admin",
  status: "pending" | "approved" | "rejected" | "suspended",
  enrolledCourses: [
    { courseId, courseName, courseThumbnail, enrolledAt }
  ],
  activeCourseId: string,
  paymentInfo: { method, paymentNumber, transactionId, screenshot },
  deviceIds: [string],
  createdAt: timestamp
}

──── courses Collection ────
{
  courseName: string,
  thumbnail: string (URL),
  price: number,
  overview: [string],
  subjects: [
    {
      subjectId: UUID,
      subjectName: string,
      chapters: [{ chapterId: UUID, chapterName: string }]
    }
  ],
  instructors: [{ name, subject, image }],
  discussionGroups: [{ name, link }],
  routinePDF: string (URL),
  allMaterialsLink: string (URL),
  order: number,
  createdAt: timestamp
}

──── videos Collection ────
{
  courseId: string,
  courseName: string,
  subjectId: string,
  subjectName: string,
  chapterId: string (optional),
  chapterName: string (optional),
  title: string,
  thumbnail: string (URL),
  videoURL: string (YouTube URL),
  pdfURL: string (URL),
  order: number,
  createdAt: timestamp
}

──── enrollRequests Collection ────
{
  userId: string,
  name: string,
  email: string,
  courseId: string,
  courseName: string,
  paymentMethod: string,
  paymentNumber: string,
  transactionId: string,
  screenshot: string (URL),
  status: "pending" | "approved" | "rejected",
  createdAt: timestamp
}

──── exams Collection ────
{
  title: string,
  courseId: string,
  subjectId: string,
  subjectName: string,
  duration: number (minutes),
  passingScore: number,
  questions: [
    { id, question, options: [4 strings], correctAnswer: 0-3 }
  ],
  isActive: boolean,
  createdAt: timestamp
}

──── settings/main_settings ────
{
  appName: string,
  appLogo: string,
  socialLinks: [{ name, link }],
  paymentMethods: [{ name, number }],
  usefulLinks: [{ name, link }],
  youtubeChannel: string,
  googleDrive: string
}

================================================================================
                     Firebase Firestore Security Rules
================================================================================

──── উভয় Firebase প্রজেক্টের জন্য একই Rules ────

Firebase Console → Firestore Database → Rules ট্যাবে নিচের কোড পেস্ট করে
"Publish" বাটনে ক্লিক করুন:

rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {

    function isAuth() {
      return request.auth != null;
    }

    function isAdmin() {
      return isAuth() &&
        get(/databases/$(database)/documents/users/$(request.auth.uid)).data.role == 'admin';
    }

    function isApproved() {
      return isAuth() &&
        get(/databases/$(database)/documents/users/$(request.auth.uid)).data.status == 'approved';
    }

    // Users — নিজের ডকুমেন্ট পড়তে/লিখতে পারবে, Admin সব পারবে
    match /users/{userId} {
      allow read: if isAuth() && (request.auth.uid == userId || isAdmin());
      allow create: if isAuth() && request.auth.uid == userId;
      allow update: if isAuth() && (request.auth.uid == userId || isAdmin());
      allow delete: if isAdmin();
    }

    // Courses — সবাই পড়তে পারবে (পাবলিক), শুধু Admin লিখতে পারবে
    match /courses/{courseId} {
      allow read: if true;
      allow write: if isAdmin();
    }

    // Videos — শুধু Approved ইউজার পড়তে পারবে, Admin লিখতে পারবে
    match /videos/{videoId} {
      allow read: if isAuth() && isApproved();
      allow write: if isAdmin();
    }

    // Enroll Requests — নিজের রিকোয়েস্ট পড়তে পারবে, Admin সব পারবে
    match /enrollRequests/{requestId} {
      allow read: if isAuth() &&
        (resource.data.userId == request.auth.uid || isAdmin());
      allow create: if isAuth();
      allow update: if isAdmin();
      allow delete: if isAdmin();
    }

    // Exams — Approved ইউজার পড়তে পারবে, Admin লিখতে পারবে
    match /exams/{examId} {
      allow read: if isAuth() && isApproved();
      allow write: if isAdmin();
    }

    // Exam Results — নিজের রেজাল্ট পড়তে/তৈরি করতে পারবে
    match /examResults/{resultId} {
      allow read: if isAuth() &&
        (resource.data.userId == request.auth.uid || isAdmin());
      allow create: if isAuth() && isApproved();
      allow update: if false;
      allow delete: if isAdmin();
    }

    // Settings — সবাই পড়তে পারবে, শুধু Admin লিখতে পারবে
    match /settings/{settingId} {
      allow read: if true;
      allow write: if isAdmin();
    }
  }
}

================================================================================
                        Capacity & Daily Limits
================================================================================

──── Firebase Free (Spark) Plan Limits ────

Resource              | Daily Limit     | Monthly
Firestore Reads       | 50,000/day      | ~1.5M/month
Firestore Writes      | 20,000/day      | ~600K/month
Firestore Deletes     | 20,000/day      | ~600K/month
Storage               | 1 GB total      | —
Auth Users            | Unlimited       | —
Bandwidth             | 10 GB/month     | —

──── প্রতি ইউজার সেশনে আনুমানিক ব্যবহার ────

Action              | Reads  | Writes
Login               | ~5     | ~2
Classroom ওপেন      | ~3     | 0
ভিডিও দেখা          | ~4     | 0
এক্সাম দেওয়া        | ~3     | ~2
Home ব্রাউজ          | ~2     | 0
মোট (গড়)           | ~17    | ~4

──── Daily Active Users (DAU) ক্যাপাসিটি ────

Scenario                          | DAU Estimate
Light Usage (5-10 ভিডিও/দিন)     | 200-300 ইউজার/দিন
Medium Usage (10-20 ভিডিও/দিন)   | 100-150 ইউজার/দিন
Heavy Usage (20+ ভিডিও/দিন)      | 50-80 ইউজার/দিন

──── Data Capacity ────

Data Type              | Estimated Limit
Total Users            | 5,000+ (Auth unlimited)
Total Courses          | 50+
Videos per Course      | 500+
Total Videos           | 5,000+
Exams                  | 500+

================================================================================
                    Firebase Free Plan Optimization Tips
================================================================================

1. ✅ Memory Caching (ইতোমধ্যে Implemented)
   - firestoreCache.ts — 5 মিনিট TTL ক্যাশ
   - ~60-70% read কমায়

2. Firestore Indexes তৈরি করুন (Firebase Console → Indexes)
   - videos: courseId (ASC) + order (ASC)
   - enrollRequests: userId (ASC) + courseId (ASC) + status (ASC)
   - examResults: examId (ASC) + userId (ASC)

3. Offline Persistence চালু করুন:
   firebase.ts ফাইলে যোগ করুন:
   import { enableIndexedDbPersistence } from "firebase/firestore";
   enableIndexedDbPersistence(db).catch(() => {});

4. Image Size ছোট রাখুন (200KB এর নিচে)

5. ✅ imgBB ব্যবহার হচ্ছে (Firebase Storage নয়) — Storage সেভ

6. ✅ Real-time Listener কমানো হয়েছে — বেশিরভাগ getDoc/getDocs ব্যবহার

7. Blaze Plan (1000+ DAU হলে):
   - $0.06/100K reads, $0.18/100K writes
   - আনুমানিক $5-15/month

================================================================================
                            App Pricing Estimate
================================================================================

──── Development Cost Breakdown (BDT) ────

Component                                          | Value (BDT)
Authentication (Email/Password, Device Limit)      | ৳15,000 - ৳25,000
User Panel (Registration, Classroom, Profile)      | ৳20,000 - ৳30,000
Video Player (YouTube, Custom Controls, Speed)     | ৳15,000 - ৳25,000
Admin Panel (Dashboard, Users, Courses, Videos)    | ৳30,000 - ৳45,000
Exam System (MCQ, Timer, Auto-grading)             | ৳15,000 - ৳20,000
Course Management (Subjects, Chapters, Groups)     | ৳15,000 - ৳20,000
AI Chatbot (Floating Assistant)                    | ৳8,000 - ৳12,000
PWA + Install                                     | ৳5,000 - ৳8,000
Data Export/Import                                 | ৳5,000 - ৳8,000
UI/UX Design (Dark/Light, Responsive)              | ৳15,000 - ৳25,000
Content Protection                                 | ৳3,000 - ৳5,000
Firebase Integration                               | ৳10,000 - ৳15,000

──── Total Estimated Value ────

Category                 | BDT                    | USD
Minimum                  | ৳1,56,000              | $1,300
Standard                 | ৳2,00,000 - ৳2,50,000  | $1,700 - $2,100
Premium (with support)   | ৳3,00,000+             | $2,500+

──── তুলনামূলক বাজার দর ────
- Teachable/Thinkific: $39-119/month ($468-1428/year)
- Custom LMS (India): $3,000-10,000
- Similar BD platforms: ৳1,50,000 - ৳5,00,000

──── মাসিক খরচ ────
- Firebase Free Plan: ৳0/month
- Firebase Blaze (1000+ DAU): ~৳500-1500/month
- imgBB API: Free
- Domain: ~৳1000/year
- মোট (Free Plan): ৳0/month

================================================================================
                           Routes & Pages
================================================================================

Route                | Page                | Access
/                    | Index Redirect      | Public
/home                | All Courses         | Public
/course/:id          | Course Details      | Public
/auth                | Login/Register      | Public
/classroom           | Classroom (Videos)  | Approved Users
/video/:id           | Video Player        | Approved Users
/exams               | Exam List           | Approved Users
/exams/:id           | Take Exam           | Approved Users
/profile             | User Profile        | Logged In
/admin               | Admin Dashboard     | Admin
/admin/users         | User Management     | Admin
/admin/courses       | Course Management   | Admin
/admin/videos        | Video Management    | Admin
/admin/videos/add    | Add Video           | Admin
/admin/exams         | Exam Management     | Admin
/admin/exams/add     | Add Exam            | Admin
/admin/settings      | App Settings        | Admin
/admin/data          | Data Export/Import   | Admin

================================================================================
                            Contact & Support
================================================================================

Developer: Md Ridoan Mahmud Zisan
Portfolio: https://ridoan-zisan.netlify.app

এই ডকুমেন্টেশন সম্পূর্ণ প্ল্যাটফর্মের বর্তমান অবস্থা প্রতিফলিত করে।
