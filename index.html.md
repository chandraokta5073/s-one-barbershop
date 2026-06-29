1. <index.html>
2. <html lang="id">
3. <head>
4. &#x20;   <meta charset="UTF-8">
5. &#x20;   <meta name="viewport" content="width=device-width, initial-scale=1.0">
6. &#x20;   <title>S ONE BARBERSHOP - Booking Online</title>
7. &#x20;   <!-- Tailwind CSS CDN -->
8. &#x20;   <script src="https://cdn.tailwindcss.com"></script>
9. &#x20;   <script>
10. &#x20;       tailwind.config = {
11. &#x20;           theme: {
12. &#x20;               extend: {
13. &#x20;                   colors: {
14. &#x20;                       brandYellow: '#FFCF40',
15. &#x20;                       brandDark: '#1A1A1A',
16. &#x20;                       brandGray: '#F3F4F6'
17. &#x20;                   }
18. &#x20;               }
19. &#x20;           }
20. &#x20;       }
21. &#x20;   </script>
22. &#x20;   <!-- Google Fonts -->
23. &#x20;   <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800\&display=swap" rel="stylesheet">
24. &#x20;   <style>
25. &#x20;       body {
26. &#x20;           font-family: 'Plus Jakarta Sans', sans-serif;
27. &#x20;           background-color: #F8F9FA;
28. &#x20;       }
29. &#x20;   </style>
30. </head>
31. <body class="flex justify-center items-start min-h-screen bg-slate-100">
32. 
33. &#x20;   <!-- Container Utama (Simulasi Device Mobile) -->
34. &#x20;   <div class="w-full max-w-md min-h-screen bg-white shadow-2xl flex flex-col relative pb-28">
35. &#x20;       
36. &#x20;       <!-- HEADER UTAMA DENGAN LATAR BELAKANG GAMBAR \& LOGO -->
37. &#x20;       <header class="text-white p-6 rounded-b-\[2.5rem] shadow-lg relative overflow-hidden bg-cover bg-center min-h-\[170px] flex items-center" 
38. &#x20;               style="background-image: linear-gradient(rgba(26, 26, 26, 0.75), rgba(26, 26, 26, 0.85)), url('https://upld.zone.id/uploads/vxir5xiq/c675e2cd-0a01-4e9d-81cb-c47aee8189d8.webp');">
39. &#x20;           <div class="flex items-center gap-4 w-full relative z-10">
40. &#x20;               <!-- Foto Logo Toko -->
41. &#x20;               <img src="https://upld.zone.id/uploads/vxir5xiq/img-0049.webp" 
42. &#x20;                    alt="S ONE Logo" 
43. &#x20;                    class="w-16 h-16 rounded-full border-2 border-brandYellow object-cover shadow-md">
44. &#x20;               <div>
45. &#x20;                   <h1 class="text-xl font-extrabold tracking-wider">S ONE BARBERSHOP</h1>
46. &#x20;                   <p class="text-xs text-brandYellow font-semibold tracking-wide mt-1">“From Ordinary to Extraordinary”</p>
47. &#x20;               </div>
48. &#x20;           </div>
49. &#x20;       </header>
50. 
51. &#x20;       <!-- JADWAL LIVE HARI INI (DI TAMPILAN AWAL) -->
52. &#x20;       <section class="p-4 border-b border-slate-100 bg-white">
53. &#x20;           <div class="flex items-center gap-2 mb-3">
54. &#x20;               <span class="relative flex h-2 w-2">
55. &#x20;                   <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-green-400 opacity-75"></span>
56. &#x20;                   <span class="relative inline-flex rounded-full h-2 w-2 bg-green-500"></span>
57. &#x20;               </span>
58. &#x20;               <h2 class="text-xs font-extrabold text-brandDark uppercase tracking-wider">Status Jadwal Hari Ini</h2>
59. &#x20;           </div>
60. &#x20;           
61. &#x20;           <!-- Tab Capster -->
62. &#x20;           <div class="flex gap-1.5 mb-3">
63. &#x20;               <button type="button" onclick="viewLiveSchedule('chandra')" id="tab-live-chandra" class="live-tab-btn flex-1 py-1.5 px-2 text-\[10px] font-bold border rounded-lg text-center transition-all bg-brandYellow text-brandDark border-brandYellow">
64. &#x20;                   Chandra
65. &#x20;               </button>
66. &#x20;               <button type="button" onclick="viewLiveSchedule('vanusa')" id="tab-live-vanusa" class="live-tab-btn flex-1 py-1.5 px-2 text-\[10px] font-bold border rounded-lg text-center transition-all bg-white text-slate-600 border-slate-200">
67. &#x20;                   Vanusa
68. &#x20;               </button>
69. &#x20;               <button type="button" onclick="viewLiveSchedule('rendi')" id="tab-live-rendi" class="live-tab-btn flex-1 py-1.5 px-2 text-\[10px] font-bold border rounded-lg text-center transition-all bg-white text-slate-600 border-slate-200">
70. &#x20;                   Rendi
71. &#x20;               </button>
72. &#x20;           </div>
73. 
74. &#x20;           <!-- Grid status slot jam hari ini -->
75. &#x20;           <div class="grid grid-cols-4 gap-1 text-\[10px]" id="live-schedule-grid">
76. &#x20;               <!-- Status diisi otomatis oleh JavaScript -->
77. &#x20;           </div>
78. &#x20;       </section>
79. 
80. &#x20;       <!-- ATURAN BOOKING -->
81. &#x20;       <div class="mx-4 mt-4 p-4 bg-amber-50 border-l-4 border-brandYellow rounded-r-xl">
82. &#x20;           <h3 class="text-xs font-bold text-amber-800 uppercase tracking-wider mb-2">Pemberitahuan \& Aturan Booking</h3>
83. &#x20;           <ul class="text-xs text-amber-900 space-y-1 list-disc list-inside">
84. &#x20;               <li>Booking minimal <strong>1 jam sebelum</strong> kedatangan.</li>
85. &#x20;               <li>Toleransi keterlambatan maksimal <strong>15 menit</strong> (selebihnya batal).</li>
86. &#x20;               <li>Satu slot booking hanya berlaku untuk <strong>1 orang</strong>.</li>
87. &#x20;               <li>Jika datang lebih awal/terlambat, harap maklum jika perlu mengantre bila capster sedang melayani pelanggan lain.</li>
88. &#x20;           </ul>
89. &#x20;       </div>
90. 
91. &#x20;       <!-- PILIH CAPSTER DENGAN FOTO -->
92. &#x20;       <section class="p-4">
93. &#x20;           <h2 class="text-sm font-extrabold text-brandDark uppercase tracking-wider mb-3">1. Pilih Capster</h2>
94. &#x20;           <div class="grid grid-cols-3 gap-3" id="capster-container">
95. &#x20;               <!-- Capster Chandra -->
96. &#x20;               <button type="button" onclick="selectCapster('chandra')" id="btn-chandra" class="capster-btn p-3 border-2 border-slate-200 rounded-xl bg-white transition-all text-center flex flex-col items-center">
97. &#x20;                   <img src="https://upld.zone.id/uploads/vxir5xiq/img-7154.webp" 
98. &#x20;                        alt="Chandra" 
99. &#x20;                        class="w-14 h-14 rounded-full object-cover mb-2 border border-slate-100">
100. &#x20;                   <span class="text-xs font-bold block text-slate-800">Chandra</span>
101. &#x20;               </button>
102. &#x20;               <!-- Capster Vanusa -->
103. &#x20;               <button type="button" onclick="selectCapster('vanusa')" id="btn-vanusa" class="capster-btn p-3 border-2 border-slate-200 rounded-xl bg-white transition-all text-center flex flex-col items-center">
104. &#x20;                   <img src="https://upld.zone.id/uploads/vxir5xiq/img-7152.webp" 
105. &#x20;                        alt="Vanusa" 
106. &#x20;                        class="w-14 h-14 rounded-full object-cover mb-2 border border-slate-100">
107. &#x20;                   <span class="text-xs font-bold block text-slate-800">Vanusa</span>
108. &#x20;               </button>
109. &#x20;               <!-- Capster Rendi -->
110. &#x20;               <button type="button" onclick="selectCapster('rendi')" id="btn-rendi" class="capster-btn p-3 border-2 border-slate-200 rounded-xl bg-white transition-all text-center flex flex-col items-center">
111. &#x20;                   <img src="https://upld.zone.id/uploads/vxir5xiq/img-7153.webp" 
112. &#x20;                        alt="Rendi" 
113. &#x20;                        class="w-14 h-14 rounded-full object-cover mb-2 border border-slate-100">
114. &#x20;                   <span class="text-xs font-bold block text-slate-800">Rendi</span>
115. &#x20;               </button>
116. &#x20;           </div>
117. &#x20;       </section>
118. 
119. &#x20;       <!-- KATALOG LAYANAN -->
120. &#x20;       <section class="p-4 hidden" id="services-section">
121. &#x20;           <div class="flex justify-between items-center mb-3">
122. &#x20;               <h2 class="text-sm font-extrabold text-brandDark uppercase tracking-wider">2. Katalog Layanan</h2>
123. &#x20;               <span class="text-xs text-slate-500 italic" id="capster-indicator"></span>
124. &#x20;           </div>
125. &#x20;           <div class="space-y-2" id="services-container">
126. &#x20;               <!-- Diisi otomatis oleh JavaScript -->
127. &#x20;           </div>
128. &#x20;       </section>
129. 
130. &#x20;       <!-- PILIH TANGGAL DAN JAM -->
131. &#x20;       <section class="p-4 hidden" id="datetime-section">
132. &#x20;           <h2 class="text-sm font-extrabold text-brandDark uppercase tracking-wider mb-3">3. Pilih Tanggal \& Jam</h2>
133. &#x20;           
134. &#x20;           <div class="mb-4">
135. &#x20;               <label class="block text-xs font-semibold text-slate-500 mb-1">Tanggal Kedatangan</label>
136. &#x20;               <input type="date" id="booking-date" onchange="onDateChange()" class="w-full p-3 border border-slate-200 rounded-xl focus:ring-2 focus:ring-brandYellow focus:border-transparent outline-none text-sm font-medium">
137. &#x20;           </div>
138. 
139. &#x20;           <div>
140. &#x20;               <label class="block text-xs font-semibold text-slate-500 mb-2">Pilihan Jam (Maks. 10 booking/hari)</label>
141. &#x20;               <div class="grid grid-cols-4 gap-2" id="slots-grid">
142. &#x20;                   <!-- Diisi otomatis oleh JavaScript -->
143. &#x20;               </div>
144. &#x20;           </div>
145. &#x20;       </section>
146. 
147. &#x20;       <!-- DATA PELANGGAN \& METODE PEMBAYARAN -->
148. &#x20;       <section class="p-4 hidden" id="customer-section">
149. &#x20;           <h2 class="text-sm font-extrabold text-brandDark uppercase tracking-wider mb-3">4. Data Diri \& Pembayaran</h2>
150. &#x20;           <div class="space-y-4">
151. &#x20;               <div>
152. &#x20;                   <label class="block text-xs font-semibold text-slate-500 mb-1">Nama Lengkap</label>
153. &#x20;                   <input type="text" id="cust-name" placeholder="Masukkan nama Anda" class="w-full p-3 border border-slate-200 rounded-xl focus:ring-2 focus:ring-brandYellow focus:border-transparent outline-none text-sm">
154. &#x20;               </div>
155. &#x20;               <div>
156. &#x20;                   <label class="block text-xs font-semibold text-slate-500 mb-1">Nomor WhatsApp</label>
157. &#x20;                   <input type="tel" id="cust-whatsapp" placeholder="Contoh: 08123456789" class="w-full p-3 border border-slate-200 rounded-xl focus:ring-2 focus:ring-brandYellow focus:border-transparent outline-none text-sm">
158. &#x20;               </div>
159. &#x20;               
160. &#x20;               <!-- PILIHAN PEMBAYARAN -->
161. &#x20;               <div>
162. &#x20;                   <label class="block text-xs font-semibold text-slate-500 mb-2">Metode Pembayaran</label>
163. &#x20;                   <div class="grid grid-cols-2 gap-3 mb-3">
164. &#x20;                       <button type="button" onclick="selectPayment('Tunai')" id="pay-tunai" class="pay-btn p-3 border-2 border-slate-200 rounded-xl bg-white text-center font-bold text-xs flex flex-col items-center justify-center gap-1">
165. &#x20;                           <span class="text-lg">💵</span>
166. &#x20;                           <span>Tunai di Kasir</span>
167. &#x20;                       </button>
168. &#x20;                       <button type="button" onclick="selectPayment('QRIS')" id="pay-qris" class="pay-btn p-3 border-2 border-slate-200 rounded-xl bg-white text-center font-bold text-xs flex flex-col items-center justify-center gap-1">
169. &#x20;                           <span class="text-lg">📱</span>
170. &#x20;                           <span>QRIS / E-Wallet</span>
171. &#x20;                       </button>
172. &#x20;                   </div>
173. &#x20;                   
174. &#x20;                   <!-- QRIS Image Box -->
175. &#x20;                   <div id="qris-container" class="hidden p-4 border border-slate-200 rounded-2xl bg-slate-50 text-center">
176. &#x20;                       <p class="text-\[11px] font-semibold text-slate-600 mb-2">Silakan scan kode QRIS ini untuk melakukan pembayaran:</p>
177. &#x20;                       <img src="https://upld.zone.id/uploads/vxir5xiq/img-0642.webp" 
178. &#x20;                            alt="QRIS S One" 
179. &#x20;                            class="mx-auto max-h-64 rounded-xl shadow-md border border-slate-200">
180. &#x20;                       <p class="text-\[10px] text-slate-400 mt-2">Simpan bukti transfer Anda setelah pembayaran selesai dilakukan.</p>
181. &#x20;                   </div>
182. &#x20;               </div>
183. &#x20;           </div>
184. &#x20;       </section>
185. 
186. &#x20;       <!-- FOOTER SUMMARY \& CART -->
187. &#x20;       <div class="fixed bottom-0 left-0 right-0 max-w-md mx-auto bg-white border-t border-slate-100 p-4 flex items-center justify-between shadow-2xl z-40">
188. &#x20;           <div>
189. &#x20;               <p class="text-\[10px] text-slate-400 font-semibold uppercase">Total Bayar</p>
190. &#x20;               <p class="text-lg font-extrabold text-brandDark" id="cart-total">Rp 0</p>
191. &#x20;           </div>
192. &#x20;           <button onclick="submitBooking()" id="btn-submit" disabled class="bg-slate-300 text-slate-500 font-bold px-6 py-3 rounded-xl text-sm transition-all cursor-not-allowed">
193. &#x20;               Booking Sekarang
194. &#x20;           </button>
195. &#x20;       </div>
196. 
197. &#x20;       <!-- MODAL SUKSES -->
198. &#x20;       <div id="success-modal" class="fixed inset-0 bg-black/60 backdrop-blur-sm z-50 flex items-center justify-center p-4 hidden">
199. &#x20;           <div class="bg-white rounded-2xl w-full max-w-xs p-6 text-center shadow-2xl transform scale-95 transition-all">
200. &#x20;               <div class="w-16 h-16 bg-green-100 text-green-600 rounded-full flex items-center justify-center mx-auto mb-4 text-3xl">✓</div>
201. &#x20;               <h3 class="text-lg font-bold text-slate-900 mb-1">Booking Berhasil!</h3>
202. &#x20;               <p class="text-xs text-slate-500 mb-4">Detail pesanan Anda telah tersimpan di sistem Google Sheet.</p>
203. &#x20;               <div class="bg-slate-50 p-3 rounded-xl text-left text-xs mb-4 space-y-1 border border-slate-100">
204. &#x20;                   <p><strong>Nama:</strong> <span id="rec-name"></span></p>
205. &#x20;                   <p><strong>Capster:</strong> <span id="rec-capster"></span></p>
206. &#x20;                   <p><strong>Tanggal:</strong> <span id="rec-date"></span></p>
207. &#x20;                   <p><strong>Jam:</strong> <span id="rec-time"></span></p>
208. &#x20;                   <p><strong>Pembayaran:</strong> <span id="rec-payment"></span></p>
209. &#x20;                   <p><strong>Total:</strong> <span id="rec-total"></span></p>
210. &#x20;               </div>
211. &#x20;               <button onclick="closeModal()" class="w-full bg-brandYellow hover:bg-yellow-400 text-brandDark font-bold py-2.5 rounded-xl text-xs transition-colors">
212. &#x20;                   Tutup \& Reset
213. &#x20;               </button>
214. &#x20;           </div>
215. &#x20;       </div>
216. 
217. &#x20;   </div>
218. 
219. &#x20;   <!-- SCRIPT UTAMA JAVASCRIPT -->
220. &#x20;   <script>
221. &#x20;       // ========================================================
222. &#x20;       // TEMPELKAN URL WEB APP YANG ANDA SALIN PADA LANGKAH 4 DI SINI:
223. &#x20;       // ========================================================
224. &#x20;       const SCRIPT\_URL = "https://script.google.com/macros/s/AKfycbwWiNrGItQ\_bqmYvFM\_99TmxlER0vFoSADDy1Hl7GJha5OUOJsOoUfqZft70wu85A09/exec";
225. 
226. &#x20;       // Database Layanan Barbershop
227. &#x20;       const capsterData = {
228. &#x20;           chandra: {
229. &#x20;               name: "Chandra",
230. &#x20;               services: \[
231. &#x20;                   { id: "c1", name: "Haircut", price: 70000 },
232. &#x20;                   { id: "c2", name: "Hair wash + massage", price: 15000 },
233. &#x20;                   { id: "c3", name: "Keratin treatment", price: 250000 },
234. &#x20;                   { id: "c4", name: "Chemical perming", price: 250000 },
235. &#x20;                   { id: "c5", name: "Cornrow", price: 350000 },
236. &#x20;                   { id: "c6", name: "Creambath", price: 150000 }
237. &#x20;               ]
238. &#x20;           },
239. &#x20;           vanusa: {
240. &#x20;               name: "Vanusa",
241. &#x20;               services: \[
242. &#x20;                   { id: "v1", name: "Haircut", price: 70000 },
243. &#x20;                   { id: "v2", name: "Hair wash + massage", price: 15000 },
244. &#x20;                   { id: "v3", name: "Creambath", price: 150000 }
245. &#x20;               ]
246. &#x20;           },
247. &#x20;           rendi: {
248. &#x20;               name: "Rendi",
249. &#x20;               services: \[
250. &#x20;                   { id: "r1", name: "Haircut", price: 70000 },
251. &#x20;                   { id: "r2", name: "Hair wash + massage", price: 15000 },
252. &#x20;                   { id: "r3", name: "Creambath", price: 150000 }
253. &#x20;               ]
254. &#x20;           }
255. &#x20;       };
256. 
257. &#x20;       const availableHours = \["10:00", "11:00", "12:00", "13:00", "14:00", "15:00", "16:00", "17:00", "18:00", "19:00", "20:00", "21:00"];
258. 
259. &#x20;       // State Aplikasi
260. &#x20;       let selectedCapster = '';
261. &#x20;       let selectedServices = \[];
262. &#x20;       let selectedDate = '';
263. &#x20;       let selectedTime = '';
264. &#x20;       let selectedPayment = '';
265. &#x20;       let currentScheduleView = 'chandra';
266. 
267. &#x20;       // Mengunci input tanggal
268. &#x20;       const dateInput = document.getElementById('booking-date');
269. &#x20;       const todayStr = new Date().toISOString().split('T')\[0];
270. &#x20;       dateInput.setAttribute('min', todayStr);
271. 
272. &#x20;       // Penyimpanan data booking lokal untuk simulasi
273. &#x20;       if (!localStorage.getItem('s\_one\_bookings')) {
274. &#x20;           localStorage.setItem('s\_one\_bookings', JSON.stringify(\[
275. &#x20;               { date: todayStr, time: "10:00", capster: "chandra" },
276. &#x20;               { date: todayStr, time: "11:00", capster: "chandra" },
277. &#x20;               { date: todayStr, time: "14:00", capster: "vanusa" },
278. &#x20;               { date: todayStr, time: "16:00", capster: "rendi" }
279. &#x20;           ]));
280. &#x20;       }
281. 
282. &#x20;       function getBookings() {
283. &#x20;           return JSON.parse(localStorage.getItem('s\_one\_bookings')) || \[];
284. &#x20;       }
285. 
286. &#x20;       // Tampilan Jadwal Live Halaman Awal
287. &#x20;       function renderLiveOverview() {
288. &#x20;           const grid = document.getElementById('live-schedule-grid');
289. &#x20;           grid.innerHTML = '';
290. &#x20;           
291. &#x20;           const bookings = getBookings();
292. &#x20;           const bookedToday = bookings.filter(b => b.date === todayStr \&\& b.capster === currentScheduleView);
293. &#x20;           const totalBookingsToday = bookedToday.length;
294. &#x20;           const isFullDay = totalBookingsToday >= 10;
295. 
296. &#x20;           const now = new Date();
297. 
298. &#x20;           availableHours.forEach(time => {
299. &#x20;               const isBooked = bookedToday.some(b => b.time === time);
300. &#x20;               
301. &#x20;               // Cek aturan minimal 1 jam sebelum
302. &#x20;               const \[slotH, slotM] = time.split(':').map(Number);
303. &#x20;               const slotTime = new Date();
304. &#x20;               slotTime.setHours(slotH, slotM, 0, 0);
305. &#x20;               const minTimeAllowed = new Date(now.getTime() + 60 \* 60 \* 1000);
306. &#x20;               const isExpired = slotTime < minTimeAllowed;
307. 
308. &#x20;               const div = document.createElement('div');
309. &#x20;               div.className = "p-1.5 border rounded text-center transition-all ";
310. 
311. &#x20;               if (isFullDay) {
312. &#x20;                   div.className += "bg-slate-100 border-slate-100 text-slate-400 opacity-50";
313. &#x20;                   div.innerText = "Penuh";
314. &#x20;               } else if (isBooked) {
315. &#x20;                   div.className += "bg-red-50 border-red-100 text-red-500 font-semibold";
316. &#x20;                   div.innerHTML = `❌ ${time}`;
317. &#x20;               } else if (isExpired) {
318. &#x20;                   div.className += "bg-slate-100 border-slate-100 text-slate-300";
319. &#x20;                   div.innerText = time;
320. &#x20;               } else {
321. &#x20;                   div.className += "bg-green-50 border-green-200 text-green-700 font-medium";
322. &#x20;                   div.innerHTML = `✓ ${time}`;
323. &#x20;               }
324. &#x20;               grid.appendChild(div);
325. &#x20;           });
326. &#x20;       }
327. 
328. &#x20;       function viewLiveSchedule(capsterKey) {
329. &#x20;           currentScheduleView = capsterKey;
330. &#x20;           
331. &#x20;           document.querySelectorAll('.live-tab-btn').forEach(btn => {
332. &#x20;               btn.classList.remove('bg-brandYellow', 'text-brandDark', 'border-brandYellow');
333. &#x20;               btn.classList.add('bg-white', 'text-slate-600', 'border-slate-200');
334. &#x20;           });
335. &#x20;           const activeBtn = document.getElementById(`tab-live-${capsterKey}`);
336. &#x20;           activeBtn.classList.remove('bg-white', 'text-slate-600', 'border-slate-200');
337. &#x20;           activeBtn.classList.add('bg-brandYellow', 'text-brandDark', 'border-brandYellow');
338. 
339. &#x20;           renderLiveOverview();
340. &#x20;       }
341. 
342. &#x20;       // Pilih Capster
343. &#x20;       function selectCapster(capsterKey) {
344. &#x20;           if (selectedCapster \&\& selectedCapster !== capsterKey \&\& selectedServices.length > 0) {
345. &#x20;               if (!confirm("Mengubah capster akan mereset pilihan layanan Anda. Lanjutkan?")) {
346. &#x20;                   return;
347. &#x20;               }
348. &#x20;           }
349. 
350. &#x20;           selectedCapster = capsterKey;
351. &#x20;           selectedServices = \[];
352. &#x20;           selectedTime = '';
353. &#x20;           updateCart();
354. 
355. &#x20;           document.querySelectorAll('.capster-btn').forEach(btn => {
356. &#x20;               btn.classList.remove('border-brandYellow', 'bg-yellow-50/50');
357. &#x20;               btn.classList.add('border-slate-200', 'bg-white');
358. &#x20;           });
359. &#x20;           const activeBtn = document.getElementById(`btn-${capsterKey}`);
360. &#x20;           activeBtn.classList.remove('border-slate-200', 'bg-white');
361. &#x20;           activeBtn.classList.add('border-brandYellow', 'bg-yellow-50/50');
362. 
363. &#x20;           document.getElementById('capster-indicator').innerText = `Capster: ${capsterData\[capsterKey].name}`;
364. &#x20;           renderServices(capsterKey);
365. &#x20;           document.getElementById('services-section').classList.remove('hidden');
366. &#x20;           document.getElementById('datetime-section').classList.remove('hidden');
367. &#x20;           renderTimeSlots();
368. &#x20;       }
369. 
370. &#x20;       // Render Layanan
371. &#x20;       function renderServices(capsterKey) {
372. &#x20;           const container = document.getElementById('services-container');
373. &#x20;           container.innerHTML = '';
374. &#x20;           
375. &#x20;           capsterData\[capsterKey].services.forEach(service => {
376. &#x20;               const isChecked = selectedServices.some(s => s.id === service.id);
377. &#x20;               const div = document.createElement('div');
378. &#x20;               div.className = `flex items-center justify-between p-3.5 border rounded-xl cursor-pointer transition-all ${
379. &#x20;                   isChecked ? 'border-brandYellow bg-amber-50/40' : 'border-slate-200 bg-white hover:border-slate-300'
380. &#x20;               }`;
381. &#x20;               div.onclick = () => toggleService(service);
382. &#x20;               div.innerHTML = `
383. &#x20;                   <div class="flex-1 pr-2">
384. &#x20;                       <p class="text-xs font-bold text-slate-800">${service.name}</p>
385. &#x20;                       <p class="text-xs text-slate-500 mt-1">Rp ${service.price.toLocaleString('id-ID')}</p>
386. &#x20;                   </div>
387. &#x20;                   <div class="w-5 h-5 border-2 ${isChecked ? 'border-brandYellow bg-brandYellow' : 'border-slate-300'} rounded-full flex items-center justify-center transition-all">
388. &#x20;                       ${isChecked ? '<span class="text-\[10px] text-brandDark font-extrabold">✓</span>' : ''}
389. &#x20;                   </div>
390. &#x20;               `;
391. &#x20;               container.appendChild(div);
392. &#x20;           });
393. &#x20;       }
394. 
395. &#x20;       function toggleService(service) {
396. &#x20;           const index = selectedServices.findIndex(s => s.id === service.id);
397. &#x20;           if (index > -1) {
398. &#x20;               selectedServices.splice(index, 1);
399. &#x20;           } else {
400. &#x20;               selectedServices.push(service);
401. &#x20;           }
402. &#x20;           renderServices(selectedCapster);
403. &#x20;           updateCart();
404. &#x20;       }
405. 
406. &#x20;       // Perubahan tanggal booking
407. &#x20;       function onDateChange() {
408. &#x20;           selectedDate = document.getElementById('booking-date').value;
409. &#x20;           selectedTime = '';
410. &#x20;           if (selectedDate) {
411. &#x20;               document.getElementById('customer-section').classList.remove('hidden');
412. &#x20;               renderTimeSlots();
413. &#x20;           }
414. &#x20;           updateCart();
415. &#x20;       }
416. 
417. &#x20;       // Pilihan Slot Jam
418. &#x20;       function renderTimeSlots() {
419. &#x20;           const grid = document.getElementById('slots-grid');
420. &#x20;           grid.innerHTML = '';
421. 
422. &#x20;           if (!selectedDate || !selectedCapster) return;
423. 
424. &#x20;           const bookings = getBookings();
425. &#x20;           const bookedForCapsterAndDate = bookings.filter(b => b.date === selectedDate \&\& b.capster === selectedCapster);
426. &#x20;           const totalBookingsToday = bookedForCapsterAndDate.length;
427. &#x20;           const isFullDay = totalBookingsToday >= 10;
428. 
429. &#x20;           const now = new Date();
430. &#x20;           const isToday = selectedDate === now.toISOString().split('T')\[0];
431. 
432. &#x20;           availableHours.forEach(time => {
433. &#x20;               const isBooked = bookedForCapsterAndDate.some(b => b.time === time);
434. &#x20;               
435. &#x20;               let isExpired = false;
436. &#x20;               if (isToday) {
437. &#x20;                   const \[slotH, slotM] = time.split(':').map(Number);
438. &#x20;                   const slotTime = new Date();
439. &#x20;                   slotTime.setHours(slotH, slotM, 0, 0);
440. &#x20;                   
441. &#x20;                   const minTimeAllowed = new Date(now.getTime() + 60 \* 60 \* 1000);
442. &#x20;                   if (slotTime < minTimeAllowed) {
443. &#x20;                       isExpired = true;
444. &#x20;                   }
445. &#x20;               }
446. 
447. &#x20;               const button = document.createElement('button');
448. &#x20;               button.type = 'button';
449. &#x20;               
450. &#x20;               if (isFullDay) {
451. &#x20;                   button.disabled = true;
452. &#x20;                   button.className = "p-2 border border-slate-100 bg-slate-100 text-slate-400 rounded-lg text-xs cursor-not-allowed opacity-50";
453. &#x20;                   button.innerText = "Penuh";
454. &#x20;               } else if (isBooked) {
455. &#x20;                   button.disabled = true;
456. &#x20;                   button.className = "p-2 border border-slate-100 bg-slate-100 text-red-400 line-through rounded-lg text-xs cursor-not-allowed";
457. &#x20;                   button.innerText = time;
458. &#x20;               } else if (isExpired) {
459. &#x20;                   button.disabled = true;
460. &#x20;                   button.className = "p-2 border border-slate-100 bg-slate-50 text-slate-300 rounded-lg text-xs cursor-not-allowed";
461. &#x20;                   button.innerText = time;
462. &#x20;               } else {
463. &#x20;                   const isSelected = selectedTime === time;
464. &#x20;                   button.className = `p-2 border rounded-lg text-xs font-semibold text-center transition-all ${
465. &#x20;                       isSelected ? 'bg-brandYellow border-brandYellow text-brandDark' : 'border-slate-200 bg-white hover:border-brandYellow text-slate-700'
466. &#x20;                   }`;
467. &#x20;                   button.innerText = time;
468. &#x20;                   button.onclick = () => selectTime(time);
469. &#x20;               }
470. 
471. &#x20;               grid.appendChild(button);
472. &#x20;           });
473. &#x20;       }
474. 
475. &#x20;       function selectTime(time) {
476. &#x20;           selectedTime = time;
477. &#x20;           renderTimeSlots();
478. &#x20;           updateCart();
479. &#x20;       }
480. 
481. &#x20;       // Pilih Metode Pembayaran
482. &#x20;       function selectPayment(method) {
483. &#x20;           selectedPayment = method;
484. &#x20;           
485. &#x20;           document.querySelectorAll('.pay-btn').forEach(btn => {
486. &#x20;               btn.classList.remove('border-brandYellow', 'bg-yellow-50/50');
487. &#x20;               btn.classList.add('border-slate-200', 'bg-white');
488. &#x20;           });
489. 
490. &#x20;           const activeBtn = document.getElementById(`pay-${method.toLowerCase()}`);
491. &#x20;           activeBtn.classList.remove('border-slate-200', 'bg-white');
492. &#x20;           activeBtn.classList.add('border-brandYellow', 'bg-yellow-50/50');
493. 
494. &#x20;           // Tampilkan QRIS Image
495. &#x20;           const qrisContainer = document.getElementById('qris-container');
496. &#x20;           if (method === 'QRIS') {
497. &#x20;               qrisContainer.classList.remove('hidden');
498. &#x20;           } else {
499. &#x20;               qrisContainer.classList.add('hidden');
500. &#x20;           }
501. 
502. &#x20;           updateCart();
503. &#x20;       }
504. 
505. &#x20;       // Validasi Keranjang \& Submit
506. &#x20;       function updateCart() {
507. &#x20;           let total = 0;
508. &#x20;           selectedServices.forEach(s => total += s.price);
509. &#x20;           document.getElementById('cart-total').innerText = `Rp ${total.toLocaleString('id-ID')}`;
510. 
511. &#x20;           const name = document.getElementById('cust-name').value.trim();
512. &#x20;           const whatsapp = document.getElementById('cust-whatsapp').value.trim();
513. &#x20;           const submitBtn = document.getElementById('btn-submit');
514. 
515. &#x20;           if (selectedCapster \&\& selectedServices.length > 0 \&\& selectedDate \&\& selectedTime \&\& name \&\& whatsapp \&\& selectedPayment) {
516. &#x20;               submitBtn.disabled = false;
517. &#x20;               submitBtn.className = "bg-brandYellow hover:bg-yellow-400 text-brandDark font-extrabold px-6 py-3 rounded-xl text-sm transition-all shadow-md active:scale-95";
518. &#x20;           } else {
519. &#x20;               submitBtn.disabled = true;
520. &#x20;               submitBtn.className = "bg-slate-300 text-slate-500 font-bold px-6 py-3 rounded-xl text-sm transition-all cursor-not-allowed";
521. &#x20;           }
522. &#x20;       }
523. 
524. &#x20;       document.getElementById('cust-name').addEventListener('input', updateCart);
525. &#x20;       document.getElementById('cust-whatsapp').addEventListener('input', updateCart);
526. 
527. &#x20;       // Pengiriman Data Form yang Kompatibel
528. &#x20;       function submitBooking() {
529. &#x20;           const name = document.getElementById('cust-name').value.trim();
530. &#x20;           const whatsapp = document.getElementById('cust-whatsapp').value.trim();
531. &#x20;           const totalStr = document.getElementById('cart-total').innerText;
532. &#x20;           const servicesStr = selectedServices.map(s => s.name).join(', ');
533. 
534. &#x20;           if (!name || !whatsapp || !selectedTime || !selectedDate || !selectedPayment) {
535. &#x20;               alert("Harap lengkapi seluruh kolom data terlebih dahulu!");
536. &#x20;               return;
537. &#x20;           }
538. 
539. &#x20;           const submitBtn = document.getElementById('btn-submit');
540. &#x20;           submitBtn.disabled = true;
541. &#x20;           submitBtn.innerText = "Memproses...";
542. 
543. &#x20;           // Simpan ke local database untuk update real-time
544. &#x20;           const bookings = getBookings();
545. &#x20;           bookings.push({
546. &#x20;               date: selectedDate,
547. &#x20;               time: selectedTime,
548. &#x20;               capster: selectedCapster,
549. &#x20;               name: name
550. &#x20;           });
551. &#x20;           localStorage.setItem('s\_one\_bookings', JSON.stringify(bookings));
552. 
553. &#x20;           // Format data URLSearchParams (Format paling aman \& bebas dari kendala CORS)
554. &#x20;           const postData = new URLSearchParams({
555. &#x20;               'Timestamp': new Date().toLocaleString('id-ID'),
556. &#x20;               'Nama': name,
557. &#x20;               'WhatsApp': whatsapp,
558. &#x20;               'Capster': capsterData\[selectedCapster].name,
559. &#x20;               'Layanan': servicesStr,
560. &#x20;               'Tanggal': selectedDate,
561. &#x20;               'Jam': selectedTime,
562. &#x20;               'Metode\_Pembayaran': selectedPayment,
563. &#x20;               'Total': totalStr
564. &#x20;           }).toString();
565. 
566. &#x20;           // POST ke Google Apps Script
567. &#x20;           fetch(SCRIPT\_URL, {
568. &#x20;               method: 'POST',
569. &#x20;               mode: 'no-cors',
570. &#x20;               headers: {
571. &#x20;                   'Content-Type': 'application/x-www-form-urlencoded'
572. &#x20;               },
573. &#x20;               body: postData
574. &#x20;           })
575. &#x20;           .then(() => {
576. &#x20;               document.getElementById('qris-container').classList.add('hidden');
577. 
578. &#x20;               // Isi data resi sukses
579. &#x20;               document.getElementById('rec-name').innerText = name;
580. &#x20;               document.getElementById('rec-capster').innerText = capsterData\[selectedCapster].name;
581. &#x20;               document.getElementById('rec-date').innerText = selectedDate;
582. &#x20;               document.getElementById('rec-time').innerText = selectedTime;
583. &#x20;               document.getElementById('rec-payment').innerText = selectedPayment;
584. &#x20;               document.getElementById('rec-total').innerText = totalStr;
585. 
586. &#x20;               document.getElementById('success-modal').classList.remove('hidden');
587. &#x20;           })
588. &#x20;           .catch(error => {
589. &#x20;               console.error('Error!', error.message);
590. &#x20;               alert("Terjadi kendala saat menyambungkan dengan server Google Sheet.");
591. &#x20;           })
592. &#x20;           .finally(() => {
593. &#x20;               submitBtn.innerText = "Booking Sekarang";
594. &#x20;               renderLiveOverview();
595. &#x20;               updateCart();
596. &#x20;           });
597. &#x20;       }
598. 
599. &#x20;       // Tutup Modal \& Reset Form ke Tampilan Awal
600. &#x20;       function closeModal() {
601. &#x20;           document.getElementById('success-modal').classList.add('hidden');
602. &#x20;           
603. &#x20;           selectedCapster = '';
604. &#x20;           selectedServices = \[];
605. &#x20;           selectedDate = '';
606. &#x20;           selectedTime = '';
607. &#x20;           selectedPayment = '';
608. 
609. &#x20;           document.getElementById('cust-name').value = '';
610. &#x20;           document.getElementById('cust-whatsapp').value = '';
611. &#x20;           document.getElementById('booking-date').value = '';
612. 
613. &#x20;           document.querySelectorAll('.capster-btn').forEach(btn => {
614. &#x20;               btn.classList.remove('border-brandYellow', 'bg-yellow-50/50');
615. &#x20;               btn.classList.add('border-slate-200', 'bg-white');
616. &#x20;           });
617. 
618. &#x20;           document.querySelectorAll('.pay-btn').forEach(btn => {
619. &#x20;               btn.classList.remove('border-brandYellow', 'bg-yellow-50/50');
620. &#x20;               btn.classList.add('border-slate-200', 'bg-white');
621. &#x20;           });
622. 
623. &#x20;           document.getElementById('services-section').classList.add('hidden');
624. &#x20;           document.getElementById('datetime-section').classList.add('hidden');
625. &#x20;           document.getElementById('customer-section').classList.add('hidden');
626. &#x20;           
627. &#x20;           renderLiveOverview();
628. &#x20;           updateCart();
629. &#x20;       }
630. 
631. &#x20;       // Memuat visual jadwal live pada halaman pertama terbuka
632. &#x20;       window.onload = function() {
633. &#x20;           renderLiveOverview();
634. &#x20;       };
635. &#x20;   </script>
636. </body>
637. </html>

