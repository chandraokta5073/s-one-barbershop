1. <!DOCTYPE html>
2. <html lang="id">
3. <head>
4. &#x20;   <meta charset="UTF-8">
5. &#x20;   <meta name="viewport" content="width=device-width, initial-scale=1.0">
6. &#x20;   <title>S ONE BARBERSHOP - Booking Online</title>
7. &#x20;   <!-- Tailwind CSS -->
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
33. &#x20;   <!-- Container Utama (Desain Responsif Mobile-First) -->
34. &#x20;   <div class="w-full max-w-md min-h-screen bg-white shadow-2xl flex flex-col relative pb-24">
35. &#x20;       
36. &#x20;       <!-- HEADER DENGAN LATAR BELAKANG GAMBAR \& LOGO BARU -->
37. &#x20;       <header class="text-white p-6 rounded-b-\[2rem] shadow-lg relative overflow-hidden bg-cover bg-center min-h-\[160px] flex items-center" 
38. &#x20;               style="background-image: linear-gradient(rgba(26, 26, 26, 0.8), rgba(26, 26, 26, 0.85)), url('https://upld.zone.id/uploads/vxir5xiq/c675e2cd-0a01-4e9d-81cb-c47aee8189d8.webp');">
39. &#x20;           <div class="flex items-center gap-4 w-full relative z-10">
40. &#x20;               <!-- Foto Logo Baru -->
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
51. &#x20;       <!-- JADWAL BOOKING HARI INI (DI TAMPILAN AWAL) -->
52. &#x20;       <section class="p-4 border-b border-slate-100 bg-white">
53. &#x20;           <div class="flex items-center gap-2 mb-2.5">
54. &#x20;               <span class="relative flex h-2 w-2">
55. &#x20;                   <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-green-400 opacity-75"></span>
56. &#x20;                   <span class="relative inline-flex rounded-full h-2 w-2 bg-green-500"></span>
57. &#x20;               </span>
58. &#x20;               <h2 class="text-xs font-extrabold text-brandDark uppercase tracking-wider">Jadwal Booking Hari Ini (Live)</h2>
59. &#x20;           </div>
60. &#x20;           
61. &#x20;           <!-- Tab Capster untuk melihat status jadwal -->
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
91. &#x20;       <!-- PILIH CAPSTER DENGAN FOTO BARU -->
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
174. &#x20;                   <!-- Box Tampilan QRIS -->
175. &#x20;                   <div id="qris-container" class="hidden p-4 border border-slate-200 rounded-2xl bg-slate-50 text-center">
176. &#x20;                       <p class="text-\[11px] font-semibold text-slate-600 mb-2">Silakan scan kode QRIS ini untuk pembayaran:</p>
177. &#x20;                       <img src="https://upld.zone.id/uploads/vxir5xiq/img-0642.webp" 
178. &#x20;                            alt="QRIS S One Barbershop" 
179. &#x20;                            class="mx-auto max-h-64 rounded-xl shadow-md border border-slate-200">
180. &#x20;                       <p class="text-\[10px] text-slate-400 mt-2">Harap simpan bukti transfer setelah melakukan pembayaran</p>
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
197. &#x20;       <!-- MODAL NOTIFIKASI SUKSES -->
198. &#x20;       <div id="success-modal" class="fixed inset-0 bg-black/60 backdrop-blur-sm z-50 flex items-center justify-center p-4 hidden">
199. &#x20;           <div class="bg-white rounded-2xl w-full max-w-xs p-6 text-center shadow-2xl transform scale-95 transition-all">
200. &#x20;               <div class="w-16 h-16 bg-green-100 text-green-600 rounded-full flex items-center justify-center mx-auto mb-4 text-3xl">✓</div>
201. &#x20;               <h3 class="text-lg font-bold text-slate-900 mb-1">Booking Berhasil!</h3>
202. &#x20;               <p class="text-xs text-slate-500 mb-4">Detail pesanan Anda telah tersimpan di sistem kami.</p>
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
219. &#x20;   <!-- SCRIPT JAVASCRIPT -->
220. &#x20;   <script>
221. &#x20;       // GANTI DENGAN URL GOOGLE APPS SCRIPT WEB APP ANDA
222. &#x20;       const SCRIPT\_URL = "https://script.google.com/macros/s/AKfycbzxxxxxxxxx/exec";
223. 
224. &#x20;       // Database Layanan Barbershop
225. &#x20;       const capsterData = {
226. &#x20;           chandra: {
227. &#x20;               name: "Chandra",
228. &#x20;               services: \[
229. &#x20;                   { id: "c1", name: "Haircut", price: 70000 },
230. &#x20;                   { id: "c2", name: "Hair wash + massage", price: 15000 },
231. &#x20;                   { id: "c3", name: "Keratin treatment", price: 250000 },
232. &#x20;                   { id: "c4", name: "Chemical perming", price: 250000 },
233. &#x20;                   { id: "c5", name: "Cornrow", price: 350000 },
234. &#x20;                   { id: "c6", name: "Creambath", price: 150000 }
235. &#x20;               ]
236. &#x20;           },
237. &#x20;           vanusa: {
238. &#x20;               name: "Vanusa",
239. &#x20;               services: \[
240. &#x20;                   { id: "v1", name: "Haircut", price: 70000 },
241. &#x20;                   { id: "v2", name: "Hair wash + massage", price: 15000 },
242. &#x20;                   { id: "v3", name: "Creambath", price: 150000 }
243. &#x20;               ]
244. &#x20;           },
245. &#x20;           rendi: {
246. &#x20;               name: "Rendi",
247. &#x20;               services: \[
248. &#x20;                   { id: "r1", name: "Haircut", price: 70000 },
249. &#x20;                   { id: "r2", name: "Hair wash + massage", price: 15000 },
250. &#x20;                   { id: "r3", name: "Creambath", price: 150000 }
251. &#x20;               ]
252. &#x20;           }
253. &#x20;       };
254. 
255. &#x20;       const availableHours = \["10:00", "11:00", "12:00", "13:00", "14:00", "15:00", "16:00", "17:00", "18:00", "19:00", "20:00", "21:00"];
256. 
257. &#x20;       // State Aplikasi
258. &#x20;       let selectedCapster = '';
259. &#x20;       let selectedServices = \[];
260. &#x20;       let selectedDate = '';
261. &#x20;       let selectedTime = '';
262. &#x20;       let selectedPayment = '';
263. &#x20;       let currentScheduleView = 'chandra'; // Tab jadwal awal default ke Chandra
264. 
265. &#x20;       // Batasan tanggal input hari ini
266. &#x20;       const dateInput = document.getElementById('booking-date');
267. &#x20;       const todayStr = new Date().toISOString().split('T')\[0];
268. &#x20;       dateInput.setAttribute('min', todayStr);
269. 
270. &#x20;       // Simulasi database booking lokal untuk memvalidasi slot penuh
271. &#x20;       if (!localStorage.getItem('s\_one\_bookings')) {
272. &#x20;           localStorage.setItem('s\_one\_bookings', JSON.stringify(\[
273. &#x20;               { date: todayStr, time: "10:00", capster: "chandra" },
274. &#x20;               { date: todayStr, time: "11:00", capster: "chandra" },
275. &#x20;               { date: todayStr, time: "14:00", capster: "vanusa" },
276. &#x20;               { date: todayStr, time: "16:00", capster: "rendi" }
277. &#x20;           ]));
278. &#x20;       }
279. 
280. &#x20;       function getBookings() {
281. &#x20;           return JSON.parse(localStorage.getItem('s\_one\_bookings')) || \[];
282. &#x20;       }
283. 
284. &#x20;       // Tampilan Jadwal Booking Live di Halaman Awal
285. &#x20;       function renderLiveOverview() {
286. &#x20;           const grid = document.getElementById('live-schedule-grid');
287. &#x20;           grid.innerHTML = '';
288. &#x20;           
289. &#x20;           const bookings = getBookings();
290. &#x20;           const bookedToday = bookings.filter(b => b.date === todayStr \&\& b.capster === currentScheduleView);
291. &#x20;           const totalBookingsToday = bookedToday.length;
292. &#x20;           const isFullDay = totalBookingsToday >= 10;
293. 
294. &#x20;           const now = new Date();
295. 
296. &#x20;           availableHours.forEach(time => {
297. &#x20;               const isBooked = bookedToday.some(b => b.time === time);
298. &#x20;               
299. &#x20;               // Cek kadaluarsa (aturan minimal 1 jam sebelum)
300. &#x20;               const \[slotH, slotM] = time.split(':').map(Number);
301. &#x20;               const slotTime = new Date();
302. &#x20;               slotTime.setHours(slotH, slotM, 0, 0);
303. &#x20;               const minTimeAllowed = new Date(now.getTime() + 60 \* 60 \* 1000);
304. &#x20;               const isExpired = slotTime < minTimeAllowed;
305. 
306. &#x20;               const div = document.createElement('div');
307. &#x20;               div.className = "p-1.5 border rounded text-center transition-all ";
308. 
309. &#x20;               if (isFullDay) {
310. &#x20;                   div.className += "bg-slate-100 border-slate-100 text-slate-400 opacity-50";
311. &#x20;                   div.innerText = "Penuh";
312. &#x20;               } else if (isBooked) {
313. &#x20;                   div.className += "bg-red-50 border-red-100 text-red-500 font-semibold";
314. &#x20;                   div.innerHTML = `❌ ${time}`;
315. &#x20;               } else if (isExpired) {
316. &#x20;                   div.className += "bg-slate-100 border-slate-100 text-slate-300";
317. &#x20;                   div.innerText = time;
318. &#x20;               } else {
319. &#x20;                   div.className += "bg-green-50 border-green-200 text-green-700 font-medium";
320. &#x20;                   div.innerHTML = `✓ ${time}`;
321. &#x20;               }
322. &#x20;               grid.appendChild(div);
323. &#x20;           });
324. &#x20;       }
325. 
326. &#x20;       // Ganti Tab Jadwal Live
327. &#x20;       function viewLiveSchedule(capsterKey) {
328. &#x20;           currentScheduleView = capsterKey;
329. &#x20;           
330. &#x20;           document.querySelectorAll('.live-tab-btn').forEach(btn => {
331. &#x20;               btn.classList.remove('bg-brandYellow', 'text-brandDark', 'border-brandYellow');
332. &#x20;               btn.classList.add('bg-white', 'text-slate-600', 'border-slate-200');
333. &#x20;           });
334. &#x20;           const activeBtn = document.getElementById(`tab-live-${capsterKey}`);
335. &#x20;           activeBtn.classList.remove('bg-white', 'text-slate-600', 'border-slate-200');
336. &#x20;           activeBtn.classList.add('bg-brandYellow', 'text-brandDark', 'border-brandYellow');
337. 
338. &#x20;           renderLiveOverview();
339. &#x20;       }
340. 
341. &#x20;       // Pilih Capster
342. &#x20;       function selectCapster(capsterKey) {
343. &#x20;           if (selectedCapster \&\& selectedCapster !== capsterKey \&\& selectedServices.length > 0) {
344. &#x20;               if (!confirm("Mengubah capster akan mereset pilihan layanan Anda. Lanjutkan?")) {
345. &#x20;                   return;
346. &#x20;               }
347. &#x20;           }
348. 
349. &#x20;           selectedCapster = capsterKey;
350. &#x20;           selectedServices = \[];
351. &#x20;           selectedTime = '';
352. &#x20;           updateCart();
353. 
354. &#x20;           document.querySelectorAll('.capster-btn').forEach(btn => {
355. &#x20;               btn.classList.remove('border-brandYellow', 'bg-yellow-50/50');
356. &#x20;               btn.classList.add('border-slate-200', 'bg-white');
357. &#x20;           });
358. &#x20;           const activeBtn = document.getElementById(`btn-${capsterKey}`);
359. &#x20;           activeBtn.classList.remove('border-slate-200', 'bg-white');
360. &#x20;           activeBtn.classList.add('border-brandYellow', 'bg-yellow-50/50');
361. 
362. &#x20;           document.getElementById('capster-indicator').innerText = `Capster: ${capsterData\[capsterKey].name}`;
363. &#x20;           renderServices(capsterKey);
364. &#x20;           document.getElementById('services-section').classList.remove('hidden');
365. &#x20;           document.getElementById('datetime-section').classList.remove('hidden');
366. &#x20;           renderTimeSlots();
367. &#x20;       }
368. 
369. &#x20;       // Render Layanan
370. &#x20;       function renderServices(capsterKey) {
371. &#x20;           const container = document.getElementById('services-container');
372. &#x20;           container.innerHTML = '';
373. &#x20;           
374. &#x20;           capsterData\[capsterKey].services.forEach(service => {
375. &#x20;               const isChecked = selectedServices.some(s => s.id === service.id);
376. &#x20;               const div = document.createElement('div');
377. &#x20;               div.className = `flex items-center justify-between p-3.5 border rounded-xl cursor-pointer transition-all ${
378. &#x20;                   isChecked ? 'border-brandYellow bg-amber-50/40' : 'border-slate-200 bg-white hover:border-slate-300'
379. &#x20;               }`;
380. &#x20;               div.onclick = () => toggleService(service);
381. &#x20;               div.innerHTML = `
382. &#x20;                   <div class="flex-1 pr-2">
383. &#x20;                       <p class="text-xs font-bold text-slate-800">${service.name}</p>
384. &#x20;                       <p class="text-xs text-slate-500 mt-1">Rp ${service.price.toLocaleString('id-ID')}</p>
385. &#x20;                   </div>
386. &#x20;                   <div class="w-5 h-5 border-2 ${isChecked ? 'border-brandYellow bg-brandYellow' : 'border-slate-300'} rounded-full flex items-center justify-center transition-all">
387. &#x20;                       ${isChecked ? '<span class="text-\[10px] text-brandDark font-extrabold">✓</span>' : ''}
388. &#x20;                   </div>
389. &#x20;               `;
390. &#x20;               container.appendChild(div);
391. &#x20;           });
392. &#x20;       }
393. 
394. &#x20;       function toggleService(service) {
395. &#x20;           const index = selectedServices.findIndex(s => s.id === service.id);
396. &#x20;           if (index > -1) {
397. &#x20;               selectedServices.splice(index, 1);
398. &#x20;           } else {
399. &#x20;               selectedServices.push(service);
400. &#x20;           }
401. &#x20;           renderServices(selectedCapster);
402. &#x20;           updateCart();
403. &#x20;       }
404. 
405. &#x20;       // Perubahan tanggal booking
406. &#x20;       function onDateChange() {
407. &#x20;           selectedDate = document.getElementById('booking-date').value;
408. &#x20;           selectedTime = '';
409. &#x20;           if (selectedDate) {
410. &#x20;               document.getElementById('customer-section').classList.remove('hidden');
411. &#x20;               renderTimeSlots();
412. &#x20;           }
413. &#x20;           updateCart();
414. &#x20;       }
415. 
416. &#x20;       // Pilihan Slot Jam
417. &#x20;       function renderTimeSlots() {
418. &#x20;           const grid = document.getElementById('slots-grid');
419. &#x20;           grid.innerHTML = '';
420. 
421. &#x20;           if (!selectedDate || !selectedCapster) return;
422. 
423. &#x20;           const bookings = getBookings();
424. &#x20;           const bookedForCapsterAndDate = bookings.filter(b => b.date === selectedDate \&\& b.capster === selectedCapster);
425. &#x20;           const totalBookingsToday = bookedForCapsterAndDate.length;
426. &#x20;           const isFullDay = totalBookingsToday >= 10;
427. 
428. &#x20;           const now = new Date();
429. &#x20;           const isToday = selectedDate === now.toISOString().split('T')\[0];
430. 
431. &#x20;           availableHours.forEach(time => {
432. &#x20;               const isBooked = bookedForCapsterAndDate.some(b => b.time === time);
433. &#x20;               
434. &#x20;               let isExpired = false;
435. &#x20;               if (isToday) {
436. &#x20;                   const \[slotH, slotM] = time.split(':').map(Number);
437. &#x20;                   const slotTime = new Date();
438. &#x20;                   slotTime.setHours(slotH, slotM, 0, 0);
439. &#x20;                   
440. &#x20;                   const minTimeAllowed = new Date(now.getTime() + 60 \* 60 \* 1000);
441. &#x20;                   if (slotTime < minTimeAllowed) {
442. &#x20;                       isExpired = true;
443. &#x20;                   }
444. &#x20;               }
445. 
446. &#x20;               const button = document.createElement('button');
447. &#x20;               button.type = 'button';
448. &#x20;               
449. &#x20;               if (isFullDay) {
450. &#x20;                   button.disabled = true;
451. &#x20;                   button.className = "p-2 border border-slate-100 bg-slate-100 text-slate-400 rounded-lg text-xs cursor-not-allowed opacity-50";
452. &#x20;                   button.innerText = "Penuh";
453. &#x20;               } else if (isBooked) {
454. &#x20;                   button.disabled = true;
455. &#x20;                   button.className = "p-2 border border-slate-100 bg-slate-100 text-red-400 line-through rounded-lg text-xs cursor-not-allowed";
456. &#x20;                   button.innerText = time;
457. &#x20;               } else if (isExpired) {
458. &#x20;                   button.disabled = true;
459. &#x20;                   button.className = "p-2 border border-slate-100 bg-slate-50 text-slate-300 rounded-lg text-xs cursor-not-allowed";
460. &#x20;                   button.innerText = time;
461. &#x20;               } else {
462. &#x20;                   const isSelected = selectedTime === time;
463. &#x20;                   button.className = `p-2 border rounded-lg text-xs font-semibold text-center transition-all ${
464. &#x20;                       isSelected ? 'bg-brandYellow border-brandYellow text-brandDark' : 'border-slate-200 bg-white hover:border-brandYellow text-slate-700'
465. &#x20;                   }`;
466. &#x20;                   button.innerText = time;
467. &#x20;                   button.onclick = () => selectTime(time);
468. &#x20;               }
469. 
470. &#x20;               grid.appendChild(button);
471. &#x20;           });
472. &#x20;       }
473. 
474. &#x20;       function selectTime(time) {
475. &#x20;           selectedTime = time;
476. &#x20;           renderTimeSlots();
477. &#x20;           updateCart();
478. &#x20;       }
479. 
480. &#x20;       // Pilih Metode Pembayaran
481. &#x20;       function selectPayment(method) {
482. &#x20;           selectedPayment = method;
483. &#x20;           
484. &#x20;           document.querySelectorAll('.pay-btn').forEach(btn => {
485. &#x20;               btn.classList.remove('border-brandYellow', 'bg-yellow-50/50');
486. &#x20;               btn.classList.add('border-slate-200', 'bg-white');
487. &#x20;           });
488. 
489. &#x20;           const activeBtn = document.getElementById(`pay-${method.toLowerCase()}`);
490. &#x20;           activeBtn.classList.remove('border-slate-200', 'bg-white');
491. &#x20;           activeBtn.classList.add('border-brandYellow', 'bg-yellow-50/50');
492. 
493. &#x20;           // Tampilkan foto QRIS jika memilih QRIS
494. &#x20;           const qrisContainer = document.getElementById('qris-container');
495. &#x20;           if (method === 'QRIS') {
496. &#x20;               qrisContainer.classList.remove('hidden');
497. &#x20;           } else {
498. &#x20;               qrisContainer.classList.add('hidden');
499. &#x20;           }
500. 
501. &#x20;           updateCart();
502. &#x20;       }
503. 
504. &#x20;       // Validasi Keranjang \& Submit
505. &#x20;       function updateCart() {
506. &#x20;           let total = 0;
507. &#x20;           selectedServices.forEach(s => total += s.price);
508. &#x20;           document.getElementById('cart-total').innerText = `Rp ${total.toLocaleString('id-ID')}`;
509. 
510. &#x20;           const name = document.getElementById('cust-name').value.trim();
511. &#x20;           const whatsapp = document.getElementById('cust-whatsapp').value.trim();
512. &#x20;           const submitBtn = document.getElementById('btn-submit');
513. 
514. &#x20;           if (selectedCapster \&\& selectedServices.length > 0 \&\& selectedDate \&\& selectedTime \&\& name \&\& whatsapp \&\& selectedPayment) {
515. &#x20;               submitBtn.disabled = false;
516. &#x20;               submitBtn.className = "bg-brandYellow hover:bg-yellow-400 text-brandDark font-extrabold px-6 py-3 rounded-xl text-sm transition-all shadow-md active:scale-95";
517. &#x20;           } else {
518. &#x20;               submitBtn.disabled = true;
519. &#x20;               submitBtn.className = "bg-slate-300 text-slate-500 font-bold px-6 py-3 rounded-xl text-sm transition-all cursor-not-allowed";
520. &#x20;           }
521. &#x20;       }
522. 
523. &#x20;       document.getElementById('cust-name').addEventListener('input', updateCart);
524. &#x20;       document.getElementById('cust-whatsapp').addEventListener('input', updateCart);
525. 
526. &#x20;       // Submit Booking ke Google Sheets \& Local Cache
527. &#x20;       function submitBooking() {
528. &#x20;           const name = document.getElementById('cust-name').value.trim();
529. &#x20;           const whatsapp = document.getElementById('cust-whatsapp').value.trim();
530. &#x20;           const totalStr = document.getElementById('cart-total').innerText;
531. &#x20;           const servicesStr = selectedServices.map(s => s.name).join(', ');
532. 
533. &#x20;           if (!name || !whatsapp || !selectedTime || !selectedDate || !selectedPayment) {
534. &#x20;               alert("Harap lengkapi seluruh data!");
535. &#x20;               return;
536. &#x20;           }
537. 
538. &#x20;           const submitBtn = document.getElementById('btn-submit');
539. &#x20;           submitBtn.disabled = true;
540. &#x20;           submitBtn.innerText = "Memproses...";
541. 
542. &#x20;           // Simpan ke local database untuk update real-time
543. &#x20;           const bookings = getBookings();
544. &#x20;           bookings.push({
545. &#x20;               date: selectedDate,
546. &#x20;               time: selectedTime,
547. &#x20;               capster: selectedCapster,
548. &#x20;               name: name
549. &#x20;           });
550. &#x20;           localStorage.setItem('s\_one\_bookings', JSON.stringify(bookings));
551. 
552. &#x20;           // Siapkan payload form data
553. &#x20;           const formData = new URLSearchParams();
554. &#x20;           formData.append('Timestamp', new Date().toLocaleString('id-ID'));
555. &#x20;           formData.append('Nama', name);
556. &#x20;           formData.append('WhatsApp', whatsapp);
557. &#x20;           formData.append('Capster', capsterData\[selectedCapster].name);
558. &#x20;           formData.append('Layanan', servicesStr);
559. &#x20;           formData.append('Tanggal', selectedDate);
560. &#x20;           formData.append('Jam', selectedTime);
561. &#x20;           formData.append('Metode\_Pembayaran', selectedPayment);
562. &#x20;           formData.append('Total', totalStr);
563. 
564. &#x20;           // POST ke Google Apps Script
565. &#x20;           fetch(SCRIPT\_URL, {
566. &#x20;               method: 'POST',
567. &#x20;               mode: 'no-cors',
568. &#x20;               body: formData
569. &#x20;           })
570. &#x20;           .then(() => {
571. &#x20;               // Sembunyikan container QRIS jika sebelumnya terbuka
572. &#x20;               document.getElementById('qris-container').classList.add('hidden');
573. 
574. &#x20;               // Tampilkan isi Resi Sukses
575. &#x20;               document.getElementById('rec-name').innerText = name;
576. &#x20;               document.getElementById('rec-capster').innerText = capsterData\[selectedCapster].name;
577. &#x20;               document.getElementById('rec-date').innerText = selectedDate;
578. &#x20;               document.getElementById('rec-time').innerText = selectedTime;
579. &#x20;               document.getElementById('rec-payment').innerText = selectedPayment;
580. &#x20;               document.getElementById('rec-total').innerText = totalStr;
581. 
582. &#x20;               document.getElementById('success-modal').classList.remove('hidden');
583. &#x20;           })
584. &#x20;           .catch(error => {
585. &#x20;               console.error('Error!', error.message);
586. &#x20;               alert("Gagal terhubung dengan server Google Sheets, namun data Anda berhasil tersimpan lokal di peranti ini.");
587. &#x20;           })
588. &#x20;           .finally(() => {
589. &#x20;               submitBtn.innerText = "Booking Sekarang";
590. &#x20;               renderLiveOverview();
591. &#x20;               updateCart();
592. &#x20;           });
593. &#x20;       }
594. 
595. &#x20;       // Tutup Modal dan Reset Form
596. &#x20;       function closeModal() {
597. &#x20;           document.getElementById('success-modal').classList.add('hidden');
598. &#x20;           
599. &#x20;           selectedCapster = '';
600. &#x20;           selectedServices = \[];
601. &#x20;           selectedDate = '';
602. &#x20;           selectedTime = '';
603. &#x20;           selectedPayment = '';
604. 
605. &#x20;           document.getElementById('cust-name').value = '';
606. &#x20;           document.getElementById('cust-whatsapp').value = '';
607. &#x20;           document.getElementById('booking-date').value = '';
608. 
609. &#x20;           document.querySelectorAll('.capster-btn').forEach(btn => {
610. &#x20;               btn.classList.remove('border-brandYellow', 'bg-yellow-50/50');
611. &#x20;               btn.classList.add('border-slate-200', 'bg-white');
612. &#x20;           });
613. 
614. &#x20;           document.querySelectorAll('.pay-btn').forEach(btn => {
615. &#x20;               btn.classList.remove('border-brandYellow', 'bg-yellow-50/50');
616. &#x20;               btn.classList.add('border-slate-200', 'bg-white');
617. &#x20;           });
618. 
619. &#x20;           document.getElementById('services-section').classList.add('hidden');
620. &#x20;           document.getElementById('datetime-section').classList.add('hidden');
621. &#x20;           document.getElementById('customer-section').classList.add('hidden');
622. &#x20;           
623. &#x20;           renderLiveOverview();
624. &#x20;           updateCart();
625. &#x20;       }
626. 
627. &#x20;       // Inisialisasi Tampilan Awal
628. &#x20;       window.onload = function() {
629. &#x20;           renderLiveOverview();
630. &#x20;       };
631. &#x20;   </script>
632. </body>
633. </html>

