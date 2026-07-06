# Seoul-tourism
首爾六天五夜
<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>首爾自由行．SEOUL TRIP</title>
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@300;400;500;700&family=Playfair+Display:ital,wght@0,400;0,600;1,400&display=swap" rel="stylesheet">
    
    <style>
        body {
            font-family: 'Noto Sans TC', sans-serif;
            background-color: #F7F5F0; /* 延伸自韓系網頁底色：溫柔奶油燕麥色 */
        }
        .serif-title {
            font-family: 'Playfair Display', serif;
        }
        /* 隱藏滾動條但保持滾動功能 */
        .no-scrollbar::-webkit-scrollbar {
            display: none;
        }
        .no-scrollbar {
            -ms-overflow-style: none;
            scrollbar-width: none;
        }
    </style>
</head>
<body class="flex justify-center min-h-screen">

    <div id="app" class="w-full max-w-md bg-[#F7F5F0] min-h-screen flex flex-col shadow-2xl relative pb-24">
        
        <div class="h-[200px] w-full bg-cover bg-center relative flex items-end px-6 pb-12" style="background-image: url('your-banner-image-url.png'); background-color: #E2E8F0;">
            <div class="absolute inset-0 bg-gradient-to-t from-black/40 to-transparent"></div>
            <div class="relative z-10 text-white">
                <span class="serif-title italic text-sm tracking-widest opacity-90 block mb-1">September 29 - October 4</span>
                <h1 class="text-2xl font-bold tracking-wider">首爾自由行 🌿</h1>
            </div>
        </div>

        <div class="flex-1 bg-[#F7F5F0] px-4 pt-6 -mt-8 rounded-t-[32px] relative z-20 shadow-[0_-10px_20px_rgba(0,0,0,0.03)]">
            
            <div class="grid grid-cols-2 gap-3 mb-6">
                <a href="https://map.naver.com/" target="_blank" class="bg-white/80 backdrop-blur-sm p-3 rounded-2xl flex items-center justify-between shadow-sm border border-[#EAE5DA]">
                    <div class="flex items-center space-x-2">
                        <span class="text-emerald-500"><i class="fa-solid fa-map-location-dot"></i></span>
                        <span class="text-xs font-medium text-gray-700">韓國找廁所 🔍화장실</span>
                    </div>
                    <i class="fa-solid fa-arrow-up-right-from-square text-[10px] text-gray-400"></i>
                </a>
                <a href="tel:1330" class="bg-white/80 backdrop-blur-sm p-3 rounded-2xl flex items-center justify-between shadow-sm border border-[#EAE5DA]">
                    <div class="flex items-center space-x-2">
                        <span class="text-rose-400"><i class="fa-solid fa-phone-volume"></i></span>
                        <span class="text-xs font-medium text-gray-700">1330 旅遊不便申訴</span>
                    </div>
                    <i class="fa-solid fa-phone text-[10px] text-gray-400"></i>
                </a>
            </div>

            <div v-if="currentTab === 'info'" class="space-y-6 animate-fadeIn">
                <div class="bg-white rounded-3xl p-5 shadow-sm border border-[#EAE5DA]">
                    <h3 class="text-sm font-bold text-gray-800 mb-4 flex items-center">
                        <span class="w-1.5 h-4 bg-[#C3D3CE] rounded-full mr-2"></span>航班資訊
                    </h3>
                    <div class="border-b border-dashed border-gray-100 pb-4 mb-4">
                        <div class="flex justify-between items-center mb-2">
                            <span class="text-xs font-semibold px-2 py-0.5 bg-[#E8EFF1] text-[#6A8E9B] rounded-md">去程 · KE2022</span>
                            <span class="text-xs text-gray-400">代號: FP9JAT</span>
                        </div>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-lg font-bold text-gray-800">13:20</p>
                                <p class="text-xs text-gray-500">桃園 T1</p>
                            </div>
                            <div class="text-center flex-1 px-4 relative">
                                <span class="text-[10px] text-gray-400 block mb-1">2h 30m</span>
                                <div class="h-[1px] bg-gray-200 w-full relative">
                                    <i class="fa-solid fa-plane text-gray-300 absolute -top-1.5 left-1/2 -translate-x-1/2 text-xs"></i>
                                </div>
                            </div>
                            <div class="text-right">
                                <p class="text-lg font-bold text-gray-800">16:50</p>
                                <p class="text-xs text-gray-500">仁川 T2</p>
                            </div>
                        </div>
                    </div>
                    <div>
                        <div class="flex justify-between items-center mb-2">
                            <span class="text-xs font-semibold px-2 py-0.5 bg-[#F5EBE6] text-[#A67C65] rounded-md">回程 · BR153</span>
                            <span class="text-xs text-gray-400">代號: FPG379</span>
                        </div>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-lg font-bold text-gray-800">13:25</p>
                                <p class="text-xs text-gray-500">仁川 T1</p>
                            </div>
                            <div class="text-center flex-1 px-4 relative">
                                <span class="text-[10px] text-gray-400 block mb-1">2h 35m</span>
                                <div class="h-[1px] bg-gray-200 w-full relative">
                                    <i class="fa-solid fa-plane text-gray-300 absolute -top-1.5 left-1/2 -translate-x-1/2 text-xs rotate-180"></i>
                                </div>
                            </div>
                            <div class="text-right">
                                <p class="text-lg font-bold text-gray-800">15:00</p>
                                <p class="text-xs text-gray-500">桃園 T2</p>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="bg-white rounded-3xl p-5 shadow-sm border border-[#EAE5DA]">
                    <h3 class="text-sm font-bold text-gray-800 mb-3 flex items-center">
                        <span class="w-1.5 h-4 bg-[#DCE5E7] rounded-full mr-2"></span>下榻酒店
                    </h3>
                    <p class="font-bold text-gray-800 text-base">江南艾琳娜飯店</p>
                    <p class="text-xs text-gray-400 mb-3">엘리에나 호텔 서울 강남</p>
                    <div class="bg-[#FBFBFA] rounded-xl p-3 flex items-center justify-between text-xs text-gray-600 mb-3">
                        <span><i class="fa-regular fa-calendar-check mr-1.5 text-gray-400"></i>9月29日 – 10月4日 (5晚)</span>
                        <a href="https://naver.me/FmGGLnn1" target="_blank" class="text-blue-500 font-medium">Naver地圖 <i class="fa-solid fa-chevron-right text-[10px]"></i></a>
                    </div>
                </div>

                <div class="bg-white rounded-3xl p-5 shadow-sm border border-[#EAE5DA]">
                    <h3 class="text-sm font-bold text-gray-800 mb-4 flex items-center">
                        <span class="w-1.5 h-4 bg-[#EADCC9] rounded-full mr-2"></span>機場接送服務
                    </h3>
                    <div class="space-y-4">
                        <div class="flex items-start space-x-3">
                            <div class="w-7 h-7 rounded-full bg-emerald-50 flex items-center justify-center text-emerald-500 text-xs shrink-0 mt-0.5">接</div>
                            <div>
                                <p class="text-xs font-bold text-gray-700">9/29 抵達接機</p>
                                <p class="text-xs text-gray-500">仁川國際機場 T2 → 江南艾琳娜飯店</p>
                            </div>
                        </div>
                        <div class="flex items-start space-x-3 border-t border-gray-100 pt-3">
                            <div class="w-7 h-7 rounded-full bg-orange-50 flex items-center justify-center text-orange-500 text-xs shrink-0 mt-0.5">送</div>
                            <div>
                                <p class="text-xs font-bold text-gray-700">10/4 09:00 送機 (預約成功)</p>
                                <p class="text-xs text-gray-500">飯店 (645 Nonhyeon-ro) → 仁川 T1 (約70分鐘)</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div v-if="currentTab === 'itinerary'" class="animate-fadeIn">
                <div class="flex space-x-2 overflow-x-auto pb-4 no-scrollbar snap-x">
                    <button v-for="day in itineraryData" :key="day.id" 
                            @click="selectedDay = day.id"
                            :class="['snap-center px-4 py-2.5 rounded-full text-xs font-medium transition-all shrink-0', 
                                    selectedDay === day.id ? 'bg-[#333333] text-white shadow-sm' : 'bg-white text-gray-500 border border-[#EAE5DA]']">
                        {{ day.title }}
                    </button>
                </div>

                <div v-for="day in itineraryData" :key="day.id" v-show="selectedDay === day.id" class="mt-2 space-y-4">
                    <p class="text-xs text-gray-400 mb-2 flex items-center"><i class="fa-regular fa-clock mr-1"></i> {{ day.note }}</p>
                    
                    <div v-for="(spot, index) in day.spots" :key="index" class="relative pl-6 border-l-2 border-dashed border-[#E3DEC3] last:border-l-0 pb-6 last:pb-2">
                        <div class="absolute -left-[7px] top-0.5 w-3 h-3 rounded-full bg-[#C1BA9E] border-2 border-[#F7F5F0]"></div>
                        
                        <div class="bg-white rounded-2xl p-4 shadow-sm border border-[#EAE5DA]">
                            <div class="flex justify-between items-start mb-2">
                                <span class="text-[10px] font-bold uppercase tracking-wider text-gray-400 block">{{ spot.time || '行程' }}</span>
                                <a v-if="spot.mapUrl" :href="getMapUrl(spot.name, spot.mapUrl)" target="_blank" class="text-[11px] font-medium text-emerald-600 bg-emerald-50 px-2.5 py-1 rounded-full flex items-center space-x-1">
                                    <i class="fa-solid fa-location-arrow text-[9px]"></i><span>導航</span>
                                </a>
                            </div>
                            <h4 class="font-bold text-sm text-gray-800 flex items-center">
                                {{ spot.name }}
                            </h4>
                            <p v-if="spot.desc" class="text-xs text-gray-500 mt-1 whitespace-pre-line leading-relaxed">{{ spot.desc }}</p>
                            
                            <div v-if="spot.transport" class="mt-3 text-[11px] text-orange-600/80 bg-orange-50/50 p-2 rounded-xl flex items-center">
                                <i class="fa-solid fa-taxi mr-1.5"></i> {{ spot.transport }}
                            </div>
                        </div>
                    </div>
                </div>
            </div>

        </div>

        <div class="absolute bottom-6 left-4 right-4 bg-white/90 backdrop-blur-md h-16 rounded-2xl shadow-xl border border-white/40 flex justify-around items-center px-4 z-50">
            <button @click="currentTab = 'info'" :class="['flex flex-col items-center space-y-1 w-16 transition-colors', currentTab === 'info' ? 'text-gray-800 font-medium' : 'text-gray-400']">
                <i class="fa-solid fa-passport text-lg"></i>
                <span class="text-[10px]">住宿航班</span>
            </button>
            <button @click="currentTab = 'itinerary'" :class="['flex flex-col items-center space-y-1 w-16 transition-colors', currentTab === 'itinerary' ? 'text-gray-800 font-medium' : 'text-gray-400']">
                <i class="fa-solid fa-calendar-days text-lg"></i>
                <span class="text-[10px]">每日行程</span>
            </button>
        </div>

    </div>

    <script>
        const { createApp, ref } = Vue;

        createApp({
            setup() {
                const currentTab = ref('itinerary'); // 預設顯示行程頁面
                const selectedDay = ref(1);

                // 行程資料結構化
                const itineraryData = ref([
                    {
                        id: 1,
                        title: "D1 9/29 (二)",
                        note: "抵達首爾與進駐飯店",
                        spots: [
                            { time: "19:00", name: "抵達飯店 🏨 Elliena Hotel", desc: "機加酒五晚皆住在江南區\n附近尋覓美味晚餐，並順手採買好隔天的早餐。", mapUrl: "https://naver.me/FmGGLnn1" }
                        ]
                    },
                    {
                        id: 2,
                        title: "D2 9/30 (三)",
                        note: "文化與街區漫遊",
                        spots: [
                            { time: "09:00", name: "出發 🚖", desc: "預計搭車車程約 30 分鐘。", transport: "🚖 前往景福宮約 30 分鐘" },
                            { time: "10:00", name: "景福宮 🔍 경복궁", desc: "已預約 10:00 幀卓旅拍 IG 攝影。\n⚠️ 現場收韓幣現金，請準備好 50 萬韓幣。\n預計停留約 4 小時（拍照 + 用餐）。" },
                            { time: "14:00", name: "北村韓屋村", desc: "首爾特別市 鐘路區 桂洞 105", mapUrl: "https://naver.me/xCjCdglo", transport: "🚖 前往廣藏市場約 8 分鐘" },
                            { time: "15:00", name: "廣藏市場 🔍 광장시장", desc: "品嚐道地街頭傳統小吃。", mapUrl: "https://naver.me/GowoJBvh", transport: "🚶 步行前往金豬烤肉約 15 分鐘" },
                            { time: "17:30", name: "金豬烤肉 (全程專人代烤)", desc: "🔍 금돼지식당 을지로점\n⭐ 推薦必點：豬五花、梅花肉、泡菜炒飯。", mapUrl: "https://naver.me/GT4yGSKd", transport: "🚖 前往公園約 17 分鐘" },
                            { time: "19:30", name: "蠶院漢江公園", desc: "欣賞首爾璀璨的漢江夜景。", mapUrl: "https://naver.me/GQG3Uwl0", transport: "🚖 返回飯店約 9 分鐘" }
                        ]
                    },
                    {
                        id: 3,
                        title: "D3 10/1 (四)",
                        note: "外郊一日遊 (KKday)",
                        spots: [
                            { time: "08:00", name: "KKday 一日遊行程 (待確認)", desc: "預計行程：鱉島花卉慶典 ＋ 南怡島 ＋ 江村鐵路自行車。\n集合地點：東大門歷史文化公園站 11 號出口 (首爾特別市 中區 乙支路六街)。", mapUrl: "https://naver.me/FuNYn78u" },
                            { time: "備案", name: "自主備案行程：永宗島看海自行車", desc: "若一日遊未成團，則自行改跑以下行程：\n1. Yeongjong Ssi側邊鐵軌腳踏車看海 (https://naver.me/xYNzykhX)\n2. Yeongjong觀光魚市場吃螃蟹 (https://naver.me/GahyapZb)\n💡 記得提早在超商買好「蝦味先」！\n3. Gueup Baetteo售票處搭船餵海鷗到月尾島 (https://naver.me/5If6HQ5b)\n4. 搭乘 Wolmimunhwauigeoriyeogui 海邊列車 (https://naver.me/Fc6YeMKQ)" }
                        ]
                    },
                    {
                        id: 4,
                        title: "D4 10/2 (五)",
                        note: "江南醫美與時尚購物",
                        spots: [
                            { time: "10:30", name: "出發", desc: "準備前往醫美預約地點。" },
                            { time: "11:00", name: "三星 BNS 醫院 🩺 (已預約)", desc: "🔍 NAVER：삼성비앤에스의원\n地址：首爾特別市 江南區 德黑蘭路 514, 三興第2大樓 9樓。\n⚠️ 醫美療程完成後，務必嚴格做好防曬、避免曝曬！", mapUrl: "https://naver.me/xnOzOyj9", transport: "🚶 步行前往大創與商場" },
                            { time: "下午", name: "大創 Coex 商場店 & 星空圖書館", desc: "漫步室內商場，朝聖超吸睛的巨大巨型星空書牆。", mapUrl: "https://naver.me/xgXtBosl", transport: "🚖 前往樂天世界塔約 14 分鐘" },
                            { time: "傍晚", name: "樂天世界塔 🔍 롯데월드타ワー", desc: "飽覽江南周邊與高空景色。", transport: "🚖 返回飯店約 25 分鐘" }
                        ]
                    },
                    {
                        id: 5,
                        title: "D5 10/3 (六)",
                        note: "浪漫秋景與世界煙火節",
                        spots: [
                            { time: "08:45", name: "KKday 一日遊：華潭森林 & 水原星空", desc: "集合地點：東大門歷史文化公園站 10 號出口 (首爾特別市 中區 乙支路七街)。", mapUrl: "https://naver.me/GJZ6SHfR" },
                            { time: "備案", name: "自主備案行程：南山與解放村", desc: "若未成行則改為：\n1. 南山公園散步 (https://naver.me/FvTLISf2)\n2. 解放村 Shin Heung 市場漫遊 (https://naver.me/5c8m7L7n)\n3. 探訪特色小店 Cat Allergy (https://naver.me/5SKd45Y7)" },
                            { time: "晚上", name: "🎆 首爾世界煙火節 (限定)", desc: "若日期完美相符，晚上將前往汝矣島浪漫賞煙火；若無則調整為悠閒市區散策後返回飯店。" }
                        ]
                    },
                    {
                        id: 6,
                        title: "D6 10/4 (日)",
                        note: "江南慢活 · 機場回台",
                        spots: [
                            { time: "09:00", name: "專車送機 🚖", desc: "預約好的司機於飯店準時接送到仁川機場 (車程約 70 分鐘)。" },
                            { time: "機場", name: "回程嚴謹通關流程", desc: "✔ 順利托運行李\n✔ 啟用 Smart Pass 快速過關\n✔ SeS 自動通關\n✔ 機場免稅店最後採購\n✔ 登機起飛回台灣 ✈️" }
                        ]
                    }
                ]);

                // 判斷裝置給予最友善的導航切換：如果在手機安裝了 Naver Map 會直接開啟，其餘環境則打開預設連結
                const getMapUrl = (name, url) => {
                    return url ? url : `https://map.naver.com/v5/search/${encodeURIComponent(name)}`;
                };

                return {
                    currentTab,
                    selectedDay,
                    itineraryData,
                    getMapUrl
                };
            }
        }).mount('#app');
    </script>
</body>
</html>
