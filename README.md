<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>জন্ম সনদ সংশোধন আবেদন ফরম</title>
    <!-- Tailwind CSS for styling -->
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <!-- html2pdf.js for PDF Generation -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.10.1/html2pdf.bundle.min.js"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Siyam+Rupali&display=swap');
        body {
            font-family: 'Siyam Rupali', Arial, sans-serif;
        }
        .pdf-container {
            width: 210mm;
            min-height: 297mm;
            padding: 20mm;
            background: white;
            margin: 0 auto;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        table, th, td {
            border: 1px solid black;
            border-collapse: collapse;
        }
        th, td {
            padding: 6px;
            font-size: 14px;
        }
    </style>
</head>
<body class="bg-gray-100 p-5">

    <div class="max-w-6xl mx-auto grid grid-cols-1 lg:grid-cols-2 gap-6">
        
        <!-- বাম পাশে: ইনপুট ফরম -->
        <div class="bg-white p-6 rounded-lg shadow-md no-print">
            <h2 class="text-xl font-bold mb-4 text-blue-600 border-b pb-2">তথ্য ইনপুট দিন</h2>
            
            <div class="space-y-4 h-[75vh] overflow-y-auto pr-2">
                <div class="grid grid-cols-2 gap-4">
                    <div>
                        <label class="block text-sm font-semibold">আবেদনের আইডি</label>
                        <input type="text" id="in-app-id" value="58125124" class="w-full border p-2 rounded">
                    </div>
                    <div>
                        <label class="block text-sm font-semibold">আবেদনের তারিখ</label>
                        <input type="text" id="in-app-date" value="20/05/2026" class="w-full border p-2 rounded">
                    </div>
                </div>

                <div>
                    <label class="block text-sm font-semibold">ইউনিয়ন পরিষদ / কার্যালয়ের নাম</label>
                    <input type="text" id="in-up-name" value="ইসলামাবাদ ইউনিয়ন পরিষদ" class="w-full border p-2 rounded">
                </div>

                <div>
                    <label class="block text-sm font-semibold">কার্যালয়ের ঠিকানা</label>
                    <input type="text" id="in-up-address" value="ইসলামাবাদ, সিদ্ধিরগঞ্জ, কচুয়াবাজার, চট্টগ্রাম বিভাগ, বাংলাদেশ" class="w-full border p-2 rounded">
                </div>

                <div class="grid grid-cols-2 gap-4">
                    <div>
                        <label class="block text-sm font-semibold">জন্ম নিবন্ধন নম্বর</label>
                        <input type="text" id="in-br-num" placeholder="এখানে লিখুন..." class="w-full border p-2 rounded">
                    </div>
                    <div>
                        <label class="block text-sm font-semibold">জন্ম নিবন্ধনের তারিখ</label>
                        <input type="text" id="in-br-date" value="05/10/2006" class="w-full border p-2 rounded">
                    </div>
                </div>

                <div class="grid grid-cols-2 gap-4">
                    <div>
                        <label class="block text-sm font-semibold">১| নিবন্ধিত ব্যক্তির নাম</label>
                        <input type="text" id="in-name" value="শফিক আলম" class="w-full border p-2 rounded">
                    </div>
                    <div>
                        <label class="block text-sm font-semibold">২| জন্ম তারিখ</label>
                        <input type="text" id="in-dob" value="02/04/1994" class="w-full border p-2 rounded">
                    </div>
                </div>

                <h3 class="font-bold text-gray-700 mt-4 border-t pt-2">৩| ভুল তথ্যের বিবরণ ও সংশোধন (সংশোধিত তথ্য):</h3>
                
                <div>
                    <label class="block text-sm font-semibold">নামের প্রথম অংশ (ইংরেজি)</label>
                    <input type="text" id="in-name-eng" value="SAFI ALAM" class="w-full border p-2 rounded">
                </div>
                <div>
                    <label class="block text-sm font-semibold">পিতার নাম (বাংলা)</label>
                    <input type="text" id="in-father-bn" value="মৃত আবুল হোসেন" class="w-full border p-2 rounded">
                </div>
                <div>
                    <label class="block text-sm font-semibold">পিতার নাম (ইংরেজি)</label>
                    <input type="text" id="in-father-eng" value="LATE ABUL HOSAN" class="w-full border p-2 rounded">
                </div>
                <div>
                    <label class="block text-sm font-semibold">মাতার নাম (বাংলা)</label>
                    <input type="text" id="in-mother-bn" value="গোল বাহার" class="w-full border p-2 rounded">
                </div>
                <div>
                    <label class="block text-sm font-semibold">মাতার নাম (ইংরেজি)</label>
                    <input type="text" id="in-mother-eng" value="GOAL BAHAR" class="w-full border p-2 rounded">
                </div>
                <div>
                    <label class="block text-sm font-semibold">জন্মস্থানের লোকেশন</label>
                    <input type="text" id="in-pob-loc" value="ইসলামাবাদ, সিদ্ধিরগঞ্জ, কচুয়াবাজার, চট্টগ্রাম বিভাগ, বাংলাদেশ" class="w-full border p-2 rounded">
                </div>
                <div>
                    <label class="block text-sm font-semibold">জন্মস্থানের ওয়ার্ড</label>
                    <input type="text" id="in-pob-ward" value="২. পাহাড়িয়াখালী, সিকদার পাড়া, উত্তর লরাবাগ" class="w-full border p-2 rounded">
                </div>
                <div>
                    <label class="block text-sm font-semibold">জন্মস্থান (বাংলায়)</label>
                    <input type="text" id="in-pob-bn" value="হোল্ডিং নং- ৪২৫ সিকদার পাড়া, ইসলামাবাদ- ৪৭০২" class="w-full border p-2 rounded">
                </div>
                <div>
                    <label class="block text-sm font-semibold">স্থায়ী ঠিকানার লোকেশন</label>
                    <input type="text" id="in-per-loc" value="ইসলামাবাদ, সিদ্ধিরগঞ্জ, কুমারবাড়ি, চট্টগ্রাম বিভাগ, বাংলাদেশ" class="w-full border p-2 rounded">
                </div>
                <div>
                    <label class="block text-sm font-semibold">স্থায়ী ঠিকানার (বাংলায়)</label>
                    <input type="text" id="in-per-bn" value="হোল্ডিং নং- ৪২৫ আউলিযাবাদ, ইসলামাবাদ- ৪৭০২" class="w-full border p-2 rounded">
                </div>
            </div>

            <button onclick="downloadPDF()" class="w-full mt-4 bg-green-600 hover:bg-green-700 text-white font-bold py-3 px-4 rounded shadow">
                Download PDF
            </button>
        </div>

        <!-- ডান পাশে: লাইভ প্রিভিউ (যা হুবহু প্রিন্ট/PDF হবে) -->
        <div class="overflow-x-auto bg-gray-200 p-2 rounded-lg">
            <div id="pdf-content" class="pdf-container text-black">
                <div class="text-right text-xs mb-2">Form Dig-4</div>
                
                <div class="flex justify-between text-sm mb-4">
                    <div>আবেদনপত্রের আইডি - <span id="lbl-app-id">58125124</span></div>
                    <div>আবেদনের তারিখ - <span id="lbl-app-date">20/05/2026</span></div>
                </div>

                <div class="text-center mb-4">
                    <h2 class="text-lg font-bold" id="lbl-up-name">ইসলামাবাদ ইউনিয়ন পরিষদ</h2>
                    <p class="text-xs text-gray-700" id="lbl-up-address">ইসলামাবাদ, সিদ্ধিরগঞ্জ, কচুয়াবাজার, চট্টগ্রাম বিভাগ, বাংলাদেশ</p>
                    <h3 class="text-md font-bold mt-2 border-b pb-1 inline-block">জন্ম সনদ সংশোধনের জন্য আবেদনপত্র</h3>
                    <p class="text-xs mt-1">[ বিধি ১৫ দ্রষ্টব্য ]</p>
                </div>

                <div class="space-y-2 text-sm mb-4">
                    <div>জন্ম নিবন্ধন নম্বর: <span id="lbl-br-num" class="border-b border-dotted px-2 font-mono"></span></div>
                    <div>জন্ম নিবন্ধনের তারিখ : <span id="lbl-br-date">05/10/2006</span> &nbsp;&nbsp;&nbsp;&nbsp; (দিন/মাস/বছর)</div>
                    <div>1| নিবন্ধিত ব্যক্তির নাম: <span id="lbl-name" class="font-bold">শফিক আলম</span></div>
                    <div>2| জন্ম তারিখ: <span id="lbl-dob">02/04/1994</span> &nbsp;&nbsp;&nbsp;&nbsp; (দিন/মাস/বছর)</div>
                    <div class="font-bold mt-2">3| ভুল তথ্যের বিবরণ ও উহার কারণ:</div>
                </div>

                <!-- টেবিল অংশ -->
                <table class="w-full text-left">
                    <thead>
                        <tr class="bg-gray-100">
                            <th class="w-1/3">সংশোধনের বিষয়</th>
                            <th class="w-1/3">সংশোধিত তথ্য</th>
                            <th class="w-1/3">সংশোধনের কারণ</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>নামের প্রথম অংশ (ইংরেজি)</td>
                            <td id="lbl-name-eng" class="font-mono text-xs">SAFI ALAM</td>
                            <td>ভুল লিপিবদ্ধ করা হয়েছিল</td>
                        </tr>
                        <tr>
                            <td>পিতার নাম (বাংলা)</td>
                            <td id="lbl-father-bn">মৃত আবুল হোসেন</td>
                            <td>ভুল লিপিবদ্ধ করা হয়েছিল</td>
                        </tr>
                        <tr>
                            <td>পিতার নাম (ইংরেজি)</td>
                            <td id="lbl-father-eng" class="font-mono text-xs">LATE ABUL HOSAN</td>
                            <td>ভুল লিপিবদ্ধ করা হয়েছিল</td>
                        </tr>
                        <tr>
                            <td>মাতার নাম (বাংলা)</td>
                            <td id="lbl-mother-bn">গোল বাহার</td>
                            <td>ভুল লিপিবদ্ধ করা হয়েছিল</td>
                        </tr>
                        <tr>
                            <td>মাতার নাম (ইংরেজি)</td>
                            <td id="lbl-mother-eng" class="font-mono text-xs">GOAL BAHAR</td>
                            <td>ভুল লিপিবদ্ধ করা হয়েছিল</td>
                        </tr>
                        <tr>
                            <td>জন্মস্থানের লোকেশন</td>
                            <td id="lbl-pob-loc" class="text-xs">ইসলামাবাদ, সিদ্ধিরগঞ্জ, কচুয়াবাজার, চট্টগ্রাম বিভাগ, বাংলাদেশ</td>
                            <td></td>
                        </tr>
                        <tr>
                            <td>জন্মস্থানের ওয়ার্ড</td>
                            <td id="lbl-pob-ward" class="text-xs">২. পাহাড়িয়াখালী, সিকদার পাড়া, উত্তর লরাবাগ</td>
                            <td></td>
                        </tr>
                        <tr>
                            <td>জন্মস্থান (বাংলায়)</td>
                            <td id="lbl-pob-bn" class="text-xs">হোল্ডিং নং- ৪২৫ সিকদার পাড়া, ...</td>
                            <td></td>
                        </tr>
                        <tr>
                            <td>স্থায়ী ঠিকানার লোকেশন</td>
                            <td id="lbl-per-loc" class="text-xs">ইসলামাবাদ, সিদ্ধিরগঞ্জ, কুমারবাড়ি, চট্টগ্রাম বিভাগ...</td>
                            <td></td>
                        </tr>
                        <tr>
                            <td>স্থায়ী ঠিকানা (বাংলায়)</td>
                            <td id="lbl-per-bn" class="text-xs">হোল্ডিং নং- ৪২৫ আউলিযাবাদ, ...</td>
                            <td></td>
                        </tr>
                    </tbody>
                </table>

                <div class="mt-6 text-sm">
                    <p class="font-bold">4| ঘোষণা :</p>
                    <p class="italic pl-4 mt-1">আমি স্বজ্ঞানে ঘোষণা করিতেছি যে উপরোক্ত তথ্য সত্য।</p>
                </div>

                <div class="mt-16 flex justify-between text-sm">
                    <div class="text-center">
                        <p class="border-t border-black pt-1 w-32 mx-auto">যাচাইকারীর স্বাক্ষর</p>
                    </div>
                    <div class="text-center">
                        <p class="border-t border-black pt-1 w-40 mx-auto">আবেদনকারীর স্বাক্ষর/টিপসই</p>
                    </div>
                </div>
            </div>
        </div>

    </div>

    <!-- JavaScript code for Dynamic sync & PDF download -->
    <script>
        // ইনপুট ফিল্ড ও লেবেলগুলোকে ম্যাপ করা
        const inputs = [
            {in: 'in-app-id', lbl: 'lbl-app-id'},
            {in: 'in-app-date', lbl: 'lbl-app-date'},
            {in: 'in-up-name', lbl: 'lbl-up-name'},
            {in: 'in-up-address', lbl: 'lbl-up-address'},
            {in: 'in-br-num', lbl: 'lbl-br-num'},
            {in: 'in-br-date', lbl: 'lbl-br-date'},
            {in: 'in-name', lbl: 'lbl-name'},
            {in: 'in-dob', lbl: 'lbl-dob'},
            {in: 'in-name-eng', lbl: 'lbl-name-eng'},
            {in: 'in-father-bn', lbl: 'lbl-father-bn'},
            {in: 'in-father-eng', lbl: 'lbl-father-eng'},
            {in: 'in-mother-bn', lbl: 'lbl-mother-bn'},
            {in: 'in-mother-eng', lbl: 'lbl-mother-eng'},
            {in: 'in-pob-loc', lbl: 'lbl-pob-loc'},
            {in: 'in-pob-ward', lbl: 'lbl-pob-ward'},
            {in: 'in-pob-bn', lbl: 'lbl-pob-bn'},
            {in: 'in-per-loc', lbl: 'lbl-per-loc'},
            {in: 'in-per-bn', lbl: 'lbl-per-bn'}
        ];

        // ইনপুট টাইপ করার সাথে সাথে প্রিভিউ আপডেট হবে
        inputs.forEach(item => {
            const inputEl = document.getElementById(item.in);
            const labelEl = document.getElementById(item.lbl);
            if(inputEl && labelEl) {
                inputEl.addEventListener('input', () => {
                    labelEl.innerText = inputEl.value;
                });
            }
        });

        // PDF ডাউনলোড করার ফাংশন
        function downloadPDF() {
            const element = document.getElementById('pdf-content');
            const appId = document.getElementById('in-app-id').value || 'application';
            
            const opt = {
                margin:       0,
                filename:     `Application_${appId}.pdf`,
                image:        { type: 'jpeg', quality: 0.98 },
                html2canvas:  { scale: 2, useCORS: true },
                jsPDF:        { unit: 'mm', format: 'a4', orientation: 'portrait' }
            };

            // HTML থেকে PDF জেনারেট এবং ডাউনলোড
            html2pdf().set(opt).from(element).save();
        }
    </script>
</body>
</html>
