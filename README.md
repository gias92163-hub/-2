<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>জন্ম সনদ সংশোধন ফরম পুরণ</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <!-- html2pdf.js -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.10.1/html2pdf.bundle.min.js"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Noto+Serif+Bengali:wght@400;700&display=swap');
        
        /* পিডিএফ তৈরির গোপন স্টাইল যা স্ক্রিনে দেখাবে না */
        #hidden-pdf-content {
            font-family: 'Noto Serif Bengali', 'Times New Roman', serif;
            width: 210mm;
            min-height: 297mm;
            padding: 12mm 15mm;
            background: white;
            color: #000;
        }
        .outer-border {
            border: 1px solid #000;
            padding: 15px;
            min-height: 270mm;
            position: relative;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 10px;
        }
        table, th, td {
            border: 1px solid #000;
        }
        th, td {
            padding: 5px 8px;
            font-size: 11px;
            vertical-align: middle;
        }
        th {
            font-weight: bold;
            text-align: center;
        }
        .dotted-line {
            border-bottom: 1px dotted #000;
            display: inline-block;
        }
    </style>
</head>
<body class="bg-slate-100 p-4 md:p-8">

    <!-- মূল ফরম ইন্টারফেস (শুধু এটাই স্ক্রিনে দেখা যাবে) -->
    <div class="max-w-3xl mx-auto bg-white p-6 rounded-xl shadow-lg border border-slate-200">
        <div class="text-center mb-6 border-b pb-4">
            <h2 class="text-2xl font-bold text-slate-800">জন্ম সনদ সংশোধন আবেদন পত্র জেনারেটর</h2>
            <p class="text-sm text-slate-500 mt-1">নিচের বক্সে তথ্যগুলো দিন এবং সরাসরি নিখুঁত PDF ডাউনলোড করুন</p>
        </div>
        
        <div class="space-y-5">
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                <div>
                    <label class="block text-sm font-bold text-slate-700 mb-1">আবেদনপত্রের আইডি</label>
                    <input type="text" id="in-app-id" value="৫৮১২৫MTI0" class="w-full border border-slate-300 p-2.5 rounded-lg focus:ring-2 focus:ring-blue-500 outline-none">
                </div>
                <div>
                    <label class="block text-sm font-bold text-slate-700 mb-1">আবেদনের তারিখ</label>
                    <input type="text" id="in-app-date" value="২৩/০১/২০২৬" class="w-full border border-slate-300 p-2.5 rounded-lg focus:ring-2 focus:ring-blue-500 outline-none">
                </div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                <div>
                    <label class="block text-sm font-bold text-slate-700 mb-1">কার্যালয়ের নাম (ইউনিয়ন/পৌরসভা)</label>
                    <input type="text" id="in-up-name" value="ইসলামাবাদ ইউনিয়ন পরিষদ" class="w-full border border-slate-300 p-2.5 rounded-lg focus:ring-2 focus:ring-blue-500 outline-none">
                </div>
                <div>
                    <label class="block text-sm font-bold text-slate-700 mb-1">কার্যালয়ের ঠিকানা</label>
                    <input type="text" id="in-up-address" value="ইসলামাবাদ, ঈদগাঁও, কক্সবাজার, চট্টগ্রাম বিভাগ, বাংলাদেশ" class="w-full border border-slate-300 p-2.5 rounded-lg focus:ring-2 focus:ring-blue-500 outline-none">
                </div>
            </div>

            <div>
                <label class="block text-sm font-bold text-slate-700 mb-1">জন্ম নিবন্ধন নম্বর</label>
                <input type="text" id="in-br-num" value="১৯৯৪২২১২৪৪২০২১৫২৩" class="w-full border border-slate-300 p-2.5 rounded-lg font-mono tracking-widest text-lg focus:ring-2 focus:ring-blue-500 outline-none">
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                <div>
                    <label class="block text-sm font-bold text-slate-700 mb-1">জন্ম নিবন্ধনের তারিখ</label>
                    <input type="text" id="in-br-date" value="০১/১০/২০০৮" class="w-full border border-slate-300 p-2.5 rounded-lg focus:ring-2 focus:ring-blue-500 outline-none">
                </div>
                <div>
                    <label class="block text-sm font-bold text-slate-700 mb-1">১| নিবন্ধিত ব্যক্তির নাম</label>
                    <input type="text" id="in-name" value="শফি আলম" class="w-full border border-slate-300 p-2.5 rounded-lg focus:ring-2 focus:ring-blue-500 outline-none">
                </div>
            </div>

            <div>
                <label class="block text-sm font-bold text-slate-700 mb-1">২| জন্ম তারিখ</label>
                <input type="text" id="in-dob" value="০২/০৫/১৯৯৪" class="w-full border border-slate-300 p-2.5 rounded-lg focus:ring-2 focus:ring-blue-500 outline-none">
            </div>

            <!-- সংশোধনী তথ্য সেকশন -->
            <div class="bg-slate-50 p-4 rounded-xl border border-slate-200 space-y-4">
                <h3 class="font-bold text-md text-blue-700 border-b pb-1">৩| টেবিলের সংশোধনীয় তথ্যাবলী</h3>
                
                <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <div>
                        <label class="block text-xs font-bold text-slate-600 mb-1">নামের প্রথম অংশ (ইংরেজি)</label>
                        <input type="text" id="t-1" value="SAFI ALAM" class="w-full border border-slate-300 p-2 rounded bg-white">
                    </div>
                    <div>
                        <label class="block text-xs font-bold text-slate-600 mb-1">পিতার নাম (বাংলা)</label>
                        <input type="text" id="t-2" value="মৃত আবুল হোসেন" class="w-full border border-slate-300 p-2 rounded bg-white">
                    </div>
                    <div>
                        <label class="block text-xs font-bold text-slate-600 mb-1">পিতার নাম (ইংরেজি)</label>
                        <input type="text" id="t-3" value="LATE ABUL HOSAN" class="w-full border border-slate-300 p-2 rounded bg-white">
                    </div>
                    <div>
                        <label class="block text-xs font-bold text-slate-600 mb-1">মাতার নাম (বাংলা)</label>
                        <input type="text" id="t-4" value="গোল বাহার" class="w-full border border-slate-300 p-2 rounded bg-white">
                    </div>
                    <div>
                        <label class="block text-xs font-bold text-slate-600 mb-1">মাতার নাম (ইংরেজি)</label>
                        <input type="text" id="t-5" value="GOAL BAHAR" class="w-full border border-slate-300 p-2 rounded bg-white">
                    </div>
                    <div>
                        <label class="block text-xs font-bold text-slate-600 mb-1">জন্মস্থানের লোকেশন</label>
                        <input type="text" id="t-6" value="ইসলামাবাদ, ঈদগাঁও, কক্সবাজার, চট্টগ্রাম বিভাগ, বাংলাদেশ" class="w-full border border-slate-300 p-2 rounded bg-white">
                    </div>
                </div>
                
                <div>
                    <label class="block text-xs font-bold text-slate-600 mb-1">জন্মস্থান (বাংলায়)</label>
                    <input type="text" id="t-9" value="হোল্ডিং নং- ৪২৫ সিকদার পাড়া, ইসলামাবাদ- ৪৭০২" class="w-full border border-slate-300 p-2 rounded bg-white">
                </div>
                <div>
                    <label class="block text-xs font-bold text-slate-600 mb-1">স্থায়ী ঠিকানার লোকেশন</label>
                    <input type="text" id="t-10" value="ইসলামাবাদ, ঈদগাঁও, কক্সবাজার, চট্টগ্রাম বিভাগ, বাংলাদেশ" class="w-full border border-slate-300 p-2 rounded bg-white">
                </div>
                <div>
                    <label class="block text-xs font-bold text-slate-600 mb-1">স্থায়ী ঠিকানা (বাংলায়)</label>
                    <input type="text" id="t-13" value="হোল্ডিং নং- ৪২৫ আউলিযাবাদ, ইসলামাবাদ- ৪৭০২" class="w-full border border-slate-300 p-2 rounded bg-white">
                </div>
            </div>

            <!-- বড় অ্যাকশন বাটন -->
            <button onclick="generateAndDownloadPDF()" class="w-full mt-4 bg-gradient-to-r from-emerald-600 to-teal-600 hover:from-emerald-700 hover:to-teal-700 text-white font-bold py-3.5 px-4 rounded-xl shadow-lg transition duration-200 transform active:scale-95 text-base flex justify-center items-center gap-2">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-4l-4 4m0 0l-4-4m4 4V4" /></svg>
                হুবহু ফরম্যাট অনুযায়ী PDF ডাউনলোড করুন
            </button>
        </div>
    </div>


    <!-- এই অংশটি স্ক্রিনে সম্পূর্ণ হাইড বা লুকানো থাকবে, কিন্তু ডাউনলোডের সময় হুবহু ছবিতে রূপান্তর হবে -->
    <div class="hidden">
        <div id="hidden-pdf-content">
            <div class="outer-border">
                
                <!-- টপ হেডার -->
                <div class="text-right text-xs font-bold mb-1">( জন্মনি ফরম-৮ )</div>
                <div class="text-right text-xs space-y-0.5 mb-2">
                    <div>আবেদনপত্রের আইডি - <span id="lbl-app-id"></span></div>
                    <div>আবেদনের তারিখ - <span id="lbl-app-date"></span></div>
                </div>

                <!-- টাইটেল -->
                <div class="text-center space-y-1 mb-3">
                    <h1 class="text-base font-bold" id="lbl-up-name"></h1>
                    <p class="text-xs" id="lbl-up-address"></p>
                    <h2 class="text-sm font-bold pt-1 inline-block">জন্ম সনদ সংশোধনের জন্য আবেদনপত্র</h2>
                    <p class="text-[11px] font-bold">[ বিধি ১৫ দ্রষ্টব্য ]</p>
                </div>

                <!-- জন্ম নিবন্ধন গ্রিড বক্স -->
                <div class="flex items-center text-xs mb-2">
                    <div class="w-1/4 font-bold text-xs">জন্ম নিবন্ধন নম্বর:</div>
                    <div class="w-3/4 border border-black p-1 font-mono tracking-[6px] text-sm font-bold pl-3" id="lbl-br-num"></div>
                </div>

                <!-- বেসিক ডিটেইলস -->
                <div class="text-xs space-y-2 mb-2">
                    <div class="flex">
                        <div class="w-1/4 font-bold">জন্ম নিবন্ধনের তারিখ :</div>
                        <div class="w-1/4"><span id="lbl-br-date"></span></div>
                        <div class="w-1/2 text-gray-700">(দিন/মাস/বৎসর)</div>
                    </div>
                    <div class="flex items-baseline">
                        <div class="w-1/4 font-bold">১| &nbsp;নিবন্ধিত ব্যক্তির নাম:</div>
                        <div class="w-3/4 dotted-line font-bold" id="lbl-name"></div>
                    </div>
                    <div class="flex">
                        <div class="w-1/4 font-bold">২| &nbsp;জন্ম তারিখ</div>
                        <div class="w-1/4"><span id="lbl-dob"></span></div>
                        <div class="w-1/2 text-gray-700">(দিন/মাস/বৎসর)</div>
                    </div>
                    <div class="font-bold pt-1">৩| &nbsp;ভুল তথ্যের বিবরণ ও উহার কারণ:</div>
                </div>

                <!-- অফিসিয়াল টেবিল স্ট্রাকচার -->
                <table>
                    <thead>
                        <tr>
                            <th class="w-[30%]">সংশোধনের বিষয়</th>
                            <th class="w-[45%]">সংশোধনীয় তথ্য</th>
                            <th class="w-[25%]">সংশোধনের কারণ</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr><td>নামের প্রথম অংশ (ইংরেজি)</td><td id="lbl-t-1" class="font-mono text-[11px]"></td><td>ভুল লিপিবদ্ধ করা হয়েছিল</td></tr>
                        <tr><td>পিতার নাম ( বাংলা )</td><td id="lbl-t-2"></td><td>ভুল লিপিবদ্ধ করা হয়েছিল</td></tr>
                        <tr><td>পিতার নাম ( ইংরেজি )</td><td id="lbl-t-3" class="font-mono text-[11px]"></td><td>ভুল লিপিবদ্ধ করা হয়েছিল</td></tr>
                        <tr><td>মাতার নাম ( বাংলা )</td><td id="lbl-t-4"></td><td>ভুল লিপিবদ্ধ করা হয়েছিল</td></tr>
                        <tr><td>মাতার নাম ( ইংরেজি )</td><td id="lbl-t-5" class="font-mono text-[11px]"></td><td>ভুল লিপিবদ্ধ করা হয়েছিল</td></tr>
                        <tr><td>জন্মস্থানের লোকেশন</td><td id="lbl-t-6"></td><td></td></tr>
                        <tr><td>জন্মস্থানের ওয়ার্ড</td><td>২. পাহাড়িযাখালী, সিকদার পাড়া, উত্তর লরাবাগ</td><td></td></tr>
                        <tr><td>জন্মস্থান (ইংরেজিতে)</td><td class="font-mono text-[10px]">HOLDING NO- 825 SIKDAR PARA, ISLAMABAD- 4702</td><td></td></tr>
                        <tr><td>জন্মস্থান (বাংলায়)</td><td id="lbl-t-9"></td><td></td></tr>
                        <tr><td>স্থায়ী ঠিকানার লোকেশন</td><td id="lbl-t-10"></td><td></td></tr>
                        <tr><td>স্থায়ী ঠিকানার ওয়ার্ড</td><td>৮. আউলিয়াবাদ, করাচিপাড়া, ওয়ায়েদেরপাড়া</td><td></td></tr>
                        <tr><td>স্থায়ী ঠিকানা (ইংরেজিতে)</td><td class="font-mono text-[10px]">HOLDING NO- 825 AOWLIYABAD, ISLAMABAD- 4702</td><td></td></tr>
                        <tr><td>স্থায়ী ঠিকানা (বাংলায়)</td><td id="lbl-t-13"></td><td></td></tr>
                        <tr><td>বর্তমান ঠিকানার লোকেশন</td><td>ইসলামাবাদ, ঈদগাঁও, কক্সবাজার, চট্টগ্রাম বিভাগ, বাংলাদেশ</td><td></td></tr>
                        <tr><td>বর্তমান ঠিকানার ওয়ার্ড</td><td>৮. আউলিয়াবাদ, করাচিপাড়া, ওয়ায়েদেরপাড়া</td><td></td></tr>
                        <tr><td>বর্তমান ঠিকানা (ইংরেজিতে)</td><td class="font-mono text-[10px]">HOLDING NO- 825 AOWLIYABAD, ISLAMABAD- 4702</td><td></td></tr>
                        <tr><td>বর্তমান ঠিকানা (বাংলায়)</td><td>হোল্ডিং নং- ৪২৫ আউলিয়াবাদ, মনোবাদ- ৪৭৫২</td><td></td></tr>
                    </tbody>
                </table>

                <!-- ঘোষণা -->
                <div class="mt-4 text-xs flex items-baseline">
                    <span class="font-bold mr-2">৪|</span>
                    <p class="font-bold text-sm">ঘোষণাঃ আমি স্বজ্ঞানে ঘোষণা করিতেছি যে উপরোক্ত তথ্য সত্য।</p>
                </div>
                
                <!-- সিগনেচার সেকশন -->
                <div class="mt-16 flex justify-between text-xs">
                    <div class="text-center"><p class="border-t border-black pt-1 w-28">যাচাইকারীর স্বাক্ষর</p></div>
                    <div class="text-center"><p class="border-t border-black pt-1 w-40">আবেদনকারীর স্বাক্ষর/টিপসই</p></div>
                </div>
            </div>
        </div>
    </div>

    <!-- JavaScript লজিক -->
    <script>
        // ফরম থেকে ডাটা ম্যাপ করার অ্যারে
        const fieldMap = [
            {in: 'in-app-id', lbl: 'lbl-app-id'},
            {in: 'in-app-date', lbl: 'lbl-app-date'},
            {in: 'in-up-name', lbl: 'lbl-up-name'},
            {in: 'in-up-address', lbl: 'lbl-up-address'},
            {in: 'in-br-num', lbl: 'lbl-br-num'},
            {in: 'in-br-date', lbl: 'lbl-br-date'},
            {in: 'in-name', lbl: 'lbl-name'},
            {in: 'in-dob', lbl: 'lbl-dob'},
            {in: 't-1', lbl: 'lbl-t-1'},
            {in: 't-2', lbl: 'lbl-t-2'},
            {in: 't-3', lbl: 'lbl-t-3'},
            {in: 't-4', lbl: 'lbl-t-4'},
            {in: 't-5', lbl: 'lbl-t-5'},
            {in: 't-6', lbl: 'lbl-t-6'},
            {in: 't-9', lbl: 'lbl-t-9'},
            {in: 't-10', lbl: 'lbl-t-10'},
            {in: 't-13', lbl: 'lbl-t-13'}
        ];

        function generateAndDownloadPDF() {
            // ১. ব্যাকগ্রাউন্ডের গোপন ফরম্যাটে সব ইনপুট পুশ করা হচ্ছে
            fieldMap.forEach(item => {
                const inputVal = document.getElementById(item.in).value;
                document.getElementById(item.lbl).innerText = inputVal;
            });

            // ২. পিডিএফ জেনারেট করার কনফিগারেশন (উচ্চ কোয়ালিটি)
            const element = document.getElementById('hidden-pdf-content');
            const appId = document.getElementById('in-app-id').value || 'Form';
            
            const opt = {
                margin:       [10, 10, 10, 10],
                filename:     `Sonsodhon_Form_${appId}.pdf`,
                image:        { type: 'jpeg', quality: 1.0 },
                html2canvas:  { scale: 3, useCORS: true, letterRendering: true, logging: false },
                jsPDF:        { unit: 'mm', format: 'a4', orientation: 'portrait' }
            };

            // ৩. প্রসেস শুরু এবং ডাউনলোড
            html2pdf().set(opt).from(element).save();
        }
    </script>
</body>
</html>
