<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>জন্ম সনদ সংশোধন আবেদন ফরম</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <!-- html2pdf.js -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.10.1/html2pdf.bundle.min.js"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Noto+Serif+Bengali:wght@400;700&display=swap');
        
        .pdf-page {
            font-family: 'Noto Serif Bengali', 'Times New Roman', serif;
            width: 210mm;
            min-height: 297mm;
            padding: 12mm 15mm;
            background: white;
            margin: 0 auto;
            color: #000;
        }
        .outer-border {
            border: 1px solid #000;
            padding: 15px;
            height: 100%;
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
            font-size: 11px;
        }
        .dotted-line {
            border-bottom: 1px dotted #000;
            display: inline-block;
        }
    </style>
</head>
<body class="bg-gray-100 p-4">

    <div class="max-w-[1600px] mx-auto grid grid-cols-1 xl:grid-cols-5 gap-6">
        
        <!-- বাম পাশে: তথ্য ইনপুট ফরম (২ কলাম জুড়ে) -->
        <div class="xl:col-span-2 bg-white p-5 rounded-lg shadow-md h-[90vh] overflow-y-auto">
            <h2 class="text-xl font-bold mb-4 text-blue-700 border-b pb-2">তথ্য পরিবর্তন ফরম</h2>
            
            <div class="space-y-4">
                <div class="grid grid-cols-2 gap-4">
                    <div>
                        <label class="block text-xs font-bold mb-1">আবেদনপত্রের আইডি</label>
                        <input type="text" id="in-app-id" value="৫৮১২৫MTI0" class="w-full border p-1.5 text-sm rounded">
                    </div>
                    <div>
                        <label class="block text-xs font-bold mb-1">আবেদনের তারিখ</label>
                        <input type="text" id="in-app-date" value="২৩/০১/২০২৬" class="w-full border p-1.5 text-sm rounded">
                    </div>
                </div>

                <div>
                    <label class="block text-xs font-bold mb-1">কার্যালয়ের নাম (ইউনিয়ন/পৌরসভা)</label>
                    <input type="text" id="in-up-name" value="ইসলামাবাদ ইউনিয়ন পরিষদ" class="w-full border p-1.5 text-sm rounded">
                </div>

                <div>
                    <label class="block text-xs font-bold mb-1">কার্যালয়ের ঠিকানা</label>
                    <input type="text" id="in-up-address" value="ইসলামাবাদ, ঈদগাঁও, কক্সবাজার, চট্টগ্রাম বিভাগ, বাংলাদেশ" class="w-full border p-1.5 text-sm rounded">
                </div>

                <div>
                    <label class="block text-xs font-bold mb-1">জন্ম নিবন্ধন নম্বর</label>
                    <input type="text" id="in-br-num" value="১৯৯৪২২১২৪৪২০২১৫২৩" class="w-full border p-1.5 text-sm rounded tracking-widest font-mono">
                </div>

                <div class="grid grid-cols-2 gap-4">
                    <div>
                        <label class="block text-xs font-bold mb-1">জন্ম নিবন্ধনের তারিখ</label>
                        <input type="text" id="in-br-date" value="০১/১০/২০০৮" class="w-full border p-1.5 text-sm rounded">
                    </div>
                    <div>
                        <label class="block text-xs font-bold mb-1">১| নিবন্ধিত ব্যক্তির নাম</label>
                        <input type="text" id="in-name" value="শফি আলম" class="w-full border p-1.5 text-sm rounded">
                    </div>
                </div>

                <div>
                    <label class="block text-xs font-bold mb-1">২| জন্ম তারিখ</label>
                    <input type="text" id="in-dob" value="০২/০৫/১৯৯৪" class="w-full border p-1.5 text-sm rounded">
                </div>

                <!-- টেবিল ডাটা ইনপুটসমূহ -->
                <h3 class="font-bold text-sm text-gray-700 mt-4 border-t pt-2 text-blue-600">৩| টেবিলের সংশোধনী তথ্যসমূহ</h3>
                
                <div class="grid grid-cols-2 gap-2">
                    <div>
                        <label class="block text-xs font-semibold">নামের প্রথম অংশ (Eng)</label>
                        <input type="text" id="t-1" value="SAFI ALAM" class="w-full border p-1 text-xs rounded">
                    </div>
                    <div>
                        <label class="block text-xs font-semibold">পিতার নাম (বাংলা)</label>
                        <input type="text" id="t-2" value="মৃত আবুল হোসেন" class="w-full border p-1 text-xs rounded">
                    </div>
                    <div>
                        <label class="block text-xs font-semibold">পিতার নাম (Eng)</label>
                        <input type="text" id="t-3" value="LATE ABUL HOSAN" class="w-full border p-1 text-xs rounded">
                    </div>
                    <div>
                        <label class="block text-xs font-semibold">মাতার নাম (বাংলা)</label>
                        <input type="text" id="t-4" value="গোল বাহার" class="w-full border p-1 text-xs rounded">
                    </div>
                    <div>
                        <label class="block text-xs font-semibold">মাতার নাম (Eng)</label>
                        <input type="text" id="t-5" value="GOAL BAHAR" class="w-full border p-1 text-xs rounded">
                    </div>
                    <div>
                        <label class="block text-xs font-semibold">জন্মস্থানের লোকেশন</label>
                        <input type="text" id="t-6" value="ইসলামাবাদ, ঈদগাঁও, কক্সবাজার, চট্টগ্রাম বিভাগ, বাংলাদেশ" class="w-full border p-1 text-xs rounded">
                    </div>
                </div>
                
                <div>
                    <label class="block text-xs font-semibold">জন্মস্থান (বাংলায়)</label>
                    <input type="text" id="t-9" value="হোল্ডিং নং- ৪২৫ সিকদার পাড়া, ইসলামাবাদ- ৪৭০২" class="w-full border p-1 text-xs rounded">
                </div>
                <div>
                    <label class="block text-xs font-semibold">স্থায়ী ঠিকানার লোকেশন</label>
                    <input type="text" id="t-10" value="ইসলামাবাদ, ঈদগাঁও, কক্সবাজার, চট্টগ্রাম বিভাগ, বাংলাদেশ" class="w-full border p-1 text-xs rounded">
                </div>
                <div>
                    <label class="block text-xs font-semibold">স্থায়ী ঠিকানা (বাংলায়)</label>
                    <input type="text" id="t-13" value="হোল্ডিং নং- ৪২৫ আউলিয়াবাদ, ইসলামাবাদ- ৪৭০২" class="w-full border p-1 text-xs rounded">
                </div>
            </div>

            <button onclick="downloadPDF()" class="w-full mt-5 bg-green-600 hover:bg-green-700 text-white font-bold py-2.5 rounded shadow text-sm">
                Download PDF
            </button>
        </div>

        <!-- ডান পাশে: হুবহু লাইভ প্রিভিউ (৩ কলাম জুড়ে) -->
        <div class="xl:col-span-3 overflow-x-auto bg-gray-300 p-4 rounded-lg flex justify-center">
            <div id="pdf-content" class="pdf-page">
                <div class="outer-border">
                    
                    <!-- টপ হেডার অংশ -->
                    <div class="text-right text-xs font-bold mb-1">( জন্মনি ফরম-৮ )</div>
                    <div class="text-right text-xs space-y-0.5 mb-2">
                        <div>আবেদনপত্রের আইডি - <span id="lbl-app-id">৫৮১২৫MTI0</span></div>
                        <div>আবেদনের তারিখ - <span id="lbl-app-date">২৩/০১/২০২৬</span></div>
                    </div>

                    <!-- মেইন টাইটেল -->
                    <div class="text-center space-y-1 mb-3">
                        <h1 class="text-base font-bold" id="lbl-up-name">ইসলামাবাদ ইউনিয়ন পরিষদ</h1>
                        <p class="text-xs" id="lbl-up-address">ইসলামাবাদ, ঈদগাঁও, কক্সবাজার, চট্টগ্রাম বিভাগ, বাংলাদেশ</p>
                        <h2 class="text-sm font-bold pt-1 inline-block">জন্ম সনদ সংশোধনের জন্য আবেদনপত্র</h2>
                        <p class="text-[11px] font-bold">[ বিধি ১৫ দ্রষ্টব্য ]</p>
                    </div>

                    <!-- জন্ম নিবন্ধন নম্বর বক্স -->
                    <div class="flex items-center text-xs mb-2">
                        <div class="w-1/4 font-bold text-xs">জন্ম নিবন্ধন নম্বর:</div>
                        <div class="w-3/4 border border-black p-1 font-mono tracking-[5px] text-sm font-bold pl-3 bg-gray-50" id="lbl-br-num">
                            ১৯৯৪২২১২৪৪২০২১৫২৩
                        </div>
                    </div>

                    <!-- জন্ম তারিখ ও নাম -->
                    <div class="text-xs space-y-2 mb-2">
                        <div class="flex">
                            <div class="w-1/4 font-bold">জন্ম নিবন্ধনের তারিখ :</div>
                            <div class="w-1/4"><span id="lbl-br-date">০১/১০/২০০৮</span></div>
                            <div class="w-1/2 text-gray-700">(দিন/মাস/বৎসর)</div>
                        </div>
                        <div class="flex items-baseline">
                            <div class="w-1/4 font-bold">১| &nbsp;নিবন্ধিত ব্যক্তির নাম:</div>
                            <div class="w-3/4 dotted-line font-bold" id="lbl-name">শফি আলম</div>
                        </div>
                        <div class="flex">
                            <div class="w-1/4 font-bold">২| &nbsp;জন্ম তারিখ</div>
                            <div class="w-1/4"><span id="lbl-dob">০২/০৫/১৯৯৪</span></div>
                            <div class="w-1/2 text-gray-700">(দিন/মাস/বৎসর)</div>
                        </div>
                        <div class="font-bold pt-1">৩| &nbsp;ভুল তথ্যের বিবরণ ও উহার কারণ:</div>
                    </div>

                    <!-- হুবহু টেবিল লেআউট -->
                    <table>
                        <thead>
                            <tr>
                                <th class="w-[30%]">সংশোধনের বিষয়</th>
                                <th class="w-[45%]">সংশোধনীয় তথ্য</th>
                                <th class="w-[25%]">সংশোধনের কারণ</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td>নামের প্রথম অংশ (ইংরেজি)</td>
                                <td id="lbl-t-1" class="font-mono text-[11px]">SAFI ALAM</td>
                                <td>ভুল লিপিবদ্ধ করা হয়েছিল</td>
                            </tr>
                            <tr>
                                <td>পিতার নাম ( বাংলা )</td>
                                <td id="lbl-t-2">মৃত আবুল হোসেন</td>
                                <td>ভুল লিপিবদ্ধ করা হয়েছিল</td>
                            </tr>
                            <tr>
                                <td>পিতার নাম ( ইংরেজি )</td>
                                <td id="lbl-t-3" class="font-mono text-[11px]">LATE ABUL HOSAN</td>
                                <td>ভুল লিপিবদ্ধ করা হয়েছিল</td>
                            </tr>
                            <tr>
                                <td>মাতার নাম ( বাংলা )</td>
                                <td id="lbl-t-4">গোল বাহার</td>
                                <td>ভুল লিপিবদ্ধ করা হয়েছিল</td>
                            </tr>
                            <tr>
                                <td>মাতার নাম ( ইংরেজি )</td>
                                <td id="lbl-t-5" class="font-mono text-[11px]">GOAL BAHAR</td>
                                <td>ভুল লিপিবদ্ধ করা হয়েছিল</td>
                            </tr>
                            <tr>
                                <td>জন্মস্থানের লোকেশন</td>
                                <td id="lbl-t-6">ইসলামাবাদ, ঈদগাঁও, কক্সবাজার, চট্টগ্রাম বিভাগ, বাংলাদেশ</td>
                                <td></td>
                            </tr>
                            <tr>
                                <td>জন্মস্থানের ওয়ার্ড</td>
                                <td>২. পাহাড়িযাখালী, সিকদার পাড়া, উত্তর লরাবাগ</td>
                                <td></td>
                            </tr>
                            <tr>
                                <td>জন্মস্থান (ইংরেজিতে)</td>
                                class="font-mono text-[10px]">HOLDING NO- 825 SIKDAR PARA, ISLAMABAD- 4702</td>
                                <td></td>
                            </tr>
                            <tr>
                                <td>জন্মস্থান (বাংলায়)</td>
                                <td id="lbl-t-9">হোল্ডিং নং- ৪২৫ সিকদার পাড়া, মনোবাদ- ৪৭৫২</td>
                                <td></td>
                            </tr>
                            <tr>
                                <td>স্থায়ী ঠিকানার লোকেশন</td>
                                <td id="lbl-t-10">ইসলামাবাদ, ঈদগাঁও, কক্সবাজার, চট্টগ্রাম বিভাগ, বাংলাদেশ</td>
                                <td></td>
                            </tr>
                            <tr>
                                <td>স্থায়ী ঠিকানার ওয়ার্ড</td>
                                <td>৮. আউলিয়াবাদ, করাচিপাড়া, ওয়ায়েদেরপাড়া</td>
                                <td></td>
                            </tr>
                            <tr>
                                <td>স্থায়ী ঠিকানা (ইংরেজিতে)</td>
                                <td class="font-mono text-[10px]">HOLDING NO- 825 AOWLIYABAD, ISLAMABAD- 4702</td>
                                <td></td>
                            </tr>
                            <tr>
                                <td>স্থায়ী ঠিকানা (বাংলায়)</td>
                                <td id="lbl-t-13">হোল্ডিং নং- ৪২৫ আউলিয়াবাদ, ইসলামাবাদ- ৪৭০২</td>
                                <td></td>
                            </tr>
                            <tr>
                                <td>বর্তমান ঠিকানার লোকেশন</td>
                                <td>ইসলামাবাদ, ঈদগাঁও, কক্সবাজার, চট্টগ্রাম বিভাগ, বাংলাদেশ</td>
                                <td></td>
                            </tr>
                            <tr>
                                <td>বর্তমান ঠিকানার ওয়ার্ড</td>
                                <td>৮. আউলিয়াবাদ, করাচিপাড়া, ওয়ায়েদেরপাড়া</td>
                                <td></td>
                            </tr>
                            <tr>
                                <td>বর্তমান ঠিকানা (ইংরেজিতে)</td>
                                <td class="font-mono text-[10px]">HOLDING NO- 825 AOWLIYABAD, ISLAMABAD- 4702</td>
                                <td></td>
                            </tr>
                            <tr>
                                <td>বর্তমান ঠিকানা (বাংলায়)</td>
                                <td>হোল্ডিং নং- ৪২৫ আউলিয়াবাদ, মনোবাদ- ৪৭৫২</td>
                                <td></td>
                            </tr>
                        </tbody>
                    </table>

                    <!-- ৪ নম্বর কলামের ঘোষণা -->
                    <div class="mt-4 text-xs flex items-baseline">
                        <span class="font-bold mr-2">৪|</span>
                        <p class="font-bold text-sm">ঘোষণাঃ আমি স্বজ্ঞানে ঘোষণা করিতেছি যে উপরোক্ত তথ্য সত্য।</p>
                    </div>

                    <!-- নিচের ডটেড বর্ডার ডিজাইন (ছবির মতো হুবহু) -->
                    <div class="absolute bottom-1 left-0 right-0 border-b-2 border-dashed border-black opacity-40"></div>
                </div>
            </div>
        </div>

    </div>

    <!-- Live Preview Sync & PDF Downloader script -->
    <script>
        const mappings = [
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

        mappings.forEach(item => {
            const inputEl = document.getElementById(item.in);
            const labelEl = document.getElementById(item.lbl);
            if(inputEl && labelEl) {
                inputEl.addEventListener('input', () => {
                    labelEl.innerText = inputEl.value;
                });
            }
        });

        function downloadPDF() {
            const element = document.getElementById('pdf-content');
            const filenameStr = document.getElementById('in-app-id').value || 'Correction_Form';
            const opt = {
                margin:       0,
                filename:     `Form_${filenameStr}.pdf`,
                image:        { type: 'jpeg', quality: 1.0 },
                html2canvas:  { scale: 3, useCORS: true, letterRendering: true },
                jsPDF:        { unit: 'mm', format: 'a4', orientation: 'portrait' }
            };
            html2pdf().set(opt).from(element).save();
        }
    </script>
</body>
</html>
