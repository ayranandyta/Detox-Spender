import React, { useState, useEffect, useMemo } from 'react';
import { 
  Wallet, 
  TrendingDown, 
  HeartHandshake, 
  Smile, 
  Frown, 
  Zap, 
  AlertTriangle, 
  Trash2, 
  PlusCircle, 
  PieChart as PieIcon, 
  Filter, 
  Sparkles,
  ShoppingBag,
  Flame,
  ShieldAlert,
  ArrowUpRight
} from 'lucide-react';

// Options for Emotions with visual icons and colors
const EMOTIONS = [
  { id: 'laper_mata', label: 'Laper Mata', icon: ShoppingBag, color: 'bg-amber-500', text: 'text-amber-500', border: 'border-amber-500/30', impulse: true, desc: 'Beli cuma gara-gara bentuknya lucu/diskon' },
  { id: 'stress', label: 'Stress / Self Reward', icon: Frown, color: 'bg-rose-500', text: 'text-rose-500', border: 'border-rose-500/30', impulse: true, desc: 'Pelarian karena capek kerja / kuliah' },
  { id: 'fomo', label: 'FOMO / Ikut Trend', icon: Flame, color: 'bg-purple-500', text: 'text-purple-500', border: 'border-purple-500/30', impulse: true, desc: 'Beli karena temen/tiktok lagi rame' },
  { id: 'kebetulan_butuh', label: 'Kebutuhan Riil', icon: ShieldAlert, color: 'bg-emerald-500', text: 'text-emerald-500', border: 'border-emerald-500/30', impulse: false, desc: 'Bener-bener butuh dan udah direncanakan' },
  { id: 'iseng', label: 'Bosan / Iseng', icon: Zap, color: 'bg-sky-500', text: 'text-sky-500', border: 'border-sky-500/30', impulse: true, desc: 'Nggak tahu mau ngapain, yaudah jajan' }
];

// Preset categories
const CATEGORIES = ['Makanan & Minuman', 'Fashion', 'Gadget & Elektronik', 'Hobi & Game', 'Skincare / Beauty', 'Lainnya'];

export default function App() {
  // State for expenses
  const [expenses, setExpenses] = useState(() => {
    const saved = localStorage.getItem('detox_spender_items');
    if (saved) {
      try { return JSON.parse(saved); } catch (e) { console.error(e); }
    }
    return [
      { id: 1, title: 'Kopi Kekinian Venti Size', amount: 48000, category: 'Makanan & Minuman', emotionId: 'stress', date: '2026-10-30', note: 'Pusing deadline revisi bos' },
      { id: 2, title: 'Token Listrik Rumah', amount: 200000, category: 'Lainnya', emotionId: 'kebetulan_butuh', date: '2026-10-29', note: 'Sudah bunyi tiit-tiit' },
      { id: 3, title: 'Baju Lucu TikTok Shop', amount: 135000, category: 'Fashion', emotionId: 'laper_mata', date: '2026-10-28', note: 'Katanya stok terbatas wkwk' },
      { id: 4, title: 'Blindbox Labubu', amount: 350000, category: 'Hobi & Game', emotionId: 'fomo', date: '2026-10-27', note: 'Biar samaan kayak temen tongkrongan' }
    ];
  });

  // Form states
  const [title, setTitle] = useState('');
  const [amount, setAmount] = useState('');
  const [category, setCategory] = useState(CATEGORIES[0]);
  const [selectedEmotion, setSelectedEmotion] = useState(EMOTIONS[0].id);
  const [note, setNote] = useState('');
  const [filterEmotion, setFilterEmotion] = useState('ALL');

  // Save to local storage on change
  useEffect(() => {
    localStorage.setItem('detox_spender_items', JSON.stringify(expenses));
  }, [expenses]);

  // Calculations
  const stats = useMemo(() => {
    let totalSpent = 0;
    let totalImpulse = 0;
    let totalNeeds = 0;
    const emotionCounts = {};

    EMOTIONS.forEach(e => { emotionCounts[e.id] = 0; });

    expenses.forEach(exp => {
      totalSpent += exp.amount;
      const emoObj = EMOTIONS.find(e => e.id === exp.emotionId);
      if (emoObj) {
        if (emoObj.impulse) {
          totalImpulse += exp.amount;
        } else {
          totalNeeds += exp.amount;
        }
        emotionCounts[exp.emotionId] = (emotionCounts[exp.emotionId] || 0) + exp.amount;
      }
    });

    const impulsePercentage = totalSpent > 0 ? Math.round((totalImpulse / totalSpent) * 100) : 0;
    const detoxScore = Math.max(0, 100 - impulsePercentage);

    // Find dominant impulse emotion
    let dominantEmotion = null;
    let maxEmotionSpent = 0;
    Object.keys(emotionCounts).forEach(emoId => {
      const isImpulse = EMOTIONS.find(e => e.id === emoId)?.impulse;
      if (isImpulse && emotionCounts[emoId] > maxEmotionSpent) {
        maxEmotionSpent = emotionCounts[emoId];
        dominantEmotion = EMOTIONS.find(e => e.id === emoId);
      }
    });

    return {
      totalSpent,
      totalImpulse,
      totalNeeds,
      impulsePercentage,
      detoxScore,
      emotionCounts,
      dominantEmotion
    };
  }, [expenses]);

  // Handle Add Expense
  const handleSubmit = (e) => {
    e.preventDefault();
    if (!title.trim() || !amount || parseFloat(amount) <= 0) return;

    const newExpense = {
      id: Date.now(),
      title: title.trim(),
      amount: parseFloat(amount),
      category,
      emotionId: selectedEmotion,
      note: note.trim(),
      date: new Date().toISOString().split('T')[0]
    };

    setExpenses([newExpense, ...expenses]);
    setTitle('');
    setAmount('');
    setNote('');
  };

  // Handle Delete
  const handleDelete = (id) => {
    setExpenses(expenses.filter(item => item.id !== id));
  };

  // Filtered List
  const filteredExpenses = useMemo(() => {
    if (filterEmotion === 'ALL') return expenses;
    return expenses.filter(item => item.emotionId === filterEmotion);
  }, [expenses, filterEmotion]);

  // Generate sarcastic feedback based on score
  const getRoastFeedback = () => {
    if (expenses.length === 0) return "Belum ada catatan nih. Yakin gak jajan hari ini?";
    if (stats.detoxScore >= 80) return "Mantap! Dompet lu aman dari godaan syaitan pengeluaran emosional. Pertahankan bang!";
    if (stats.detoxScore >= 50) return "Lumayan lah, tapi lu masih sering 'laper mata' nih. Jangan sering-sering bohongin diri sendiri pake kedok 'Self Reward' ya!";
    if (stats.detoxScore >= 25) return "BAHAYA! Hampir mayoritas duit lu melayang cuma gara-gara turutan emosi sesaat. Istighfar yuk!";
    return "PARAH BANGT! Dompet lu jebol gara-gara emosi lu sendiri. Mending uninstall e-wallet dulu deh!";
  };

  return (
    <div className="min-h-screen bg-slate-950 text-slate-100 font-sans p-4 md:p-8">
      <div className="max-w-6xl mx-auto space-y-8">
        
        {/* HEADER SECTION */}
        <header className="flex flex-col md:flex-row justify-between items-start md:items-center pb-6 border-b border-slate-800 gap-4">
          <div>
            <div className="flex items-center gap-3">
              <div className="p-3 bg-gradient-to-tr from-rose-600 to-amber-500 rounded-2xl shadow-lg shadow-rose-500/20">
                <HeartHandshake className="w-8 h-8 text-white" />
              </div>
              <div>
                <h1 className="text-3xl font-extrabold tracking-tight bg-gradient-to-r from-white via-slate-200 to-slate-400 bg-clip-text text-transparent">
                  Detox Spender
                </h1>
                <p className="text-sm text-slate-400">Budgeting Pake Emosi: Cek Seberapa 'Laper Mata' Lu Hari Ini</p>
              </div>
            </div>
          </div>

          <div className="flex items-center gap-3 bg-slate-900 border border-slate-800 px-4 py-2.5 rounded-2xl">
            <Wallet className="w-5 h-5 text-emerald-400" />
            <div>
              <p className="text-xs text-slate-400">Total Pengeluaran</p>
              <p className="text-lg font-bold text-slate-100">
                Rp {stats.totalSpent.toLocaleString('id-ID')}
              </p>
            </div>
          </div>
        </header>

        {/* DASHBOARD STATS SECTION */}
        <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
          
          {/* Detox Score Card */}
          <div className="bg-slate-900 border border-slate-800 rounded-3xl p-6 relative overflow-hidden flex flex-col justify-between">
            <div className="flex justify-between items-start">
              <div>
                <p className="text-sm text-slate-400 font-medium">Detox Wallet Score</p>
                <h2 className="text-4xl font-extrabold mt-2 text-white">{stats.detoxScore}<span className="text-xl text-slate-500">/100</span></h2>
              </div>
              <div className={`p-3 rounded-2xl ${stats.detoxScore > 60 ? 'bg-emerald-500/10 text-emerald-400' : 'bg-rose-500/10 text-rose-400'}`}>
                {stats.detoxScore > 60 ? <Smile className="w-6 h-6" /> : <Frown className="w-6 h-6" />}
              </div>
            </div>
            
            {/* Progress bar */}
            <div className="mt-6 space-y-2">
              <div className="w-full bg-slate-800 rounded-full h-3 overflow-hidden">
                <div 
                  className={`h-full transition-all duration-500 ${
                    stats.detoxScore > 60 ? 'bg-emerald-500' : stats.detoxScore > 35 ? 'bg-amber-500' : 'bg-rose-500'
                  }`}
                  style={{ width: `${stats.detoxScore}%` }}
                />
              </div>
              <p className="text-xs text-slate-400 flex items-center gap-1.5 mt-2">
                <Sparkles className="w-4 h-4 text-amber-400 shrink-0" />
                <span>{getRoastFeedback()}</span>
              </p>
            </div>
          </div>

          {/* Impulse vs Needs Card */}
          <div className="bg-slate-900 border border-slate-800 rounded-3xl p-6 flex flex-col justify-between">
            <div>
              <p className="text-sm text-slate-400 font-medium">Impulse Barometer</p>
              <div className="flex items-baseline gap-2 mt-2">
                <span className="text-3xl font-bold text-rose-400">{stats.impulsePercentage}%</span>
                <span className="text-xs text-slate-400">Pengeluaran Emosional</span>
              </div>
            </div>

            <div className="space-y-3 mt-4">
              <div className="flex justify-between text-xs">
                <span className="text-rose-400 flex items-center gap-1">● Emosi / Impulse</span>
                <span className="font-semibold text-slate-200">Rp {stats.totalImpulse.toLocaleString('id-ID')}</span>
              </div>
              <div className="flex justify-between text-xs">
                <span className="text-emerald-400 flex items-center gap-1">● Kebutuhan Riil</span>
                <span className="font-semibold text-slate-200">Rp {stats.totalNeeds.toLocaleString('id-ID')}</span>
              </div>
              <div className="w-full bg-emerald-500/20 rounded-full h-3 overflow-hidden flex">
                <div 
                  className="bg-rose-500 h-full transition-all duration-500"
                  style={{ width: `${stats.impulsePercentage}%` }}
                />
              </div>
            </div>
          </div>

          {/* Dominant Emotion Card */}
          <div className="bg-slate-900 border border-slate-800 rounded-3xl p-6 flex flex-col justify-between">
            <div>
              <p className="text-sm text-slate-400 font-medium">Musuh Utama Dompet Lu</p>
              {stats.dominantEmotion ? (
                <div className="mt-3 flex items-center gap-3">
                  <div className={`p-3 rounded-2xl ${stats.dominantEmotion.color} text-white`}>
                    <stats.dominantEmotion.icon className="w-6 h-6" />
                  </div>
                  <div>
                    <h3 className="text-xl font-bold text-white">{stats.dominantEmotion.label}</h3>
                    <p className="text-xs text-slate-400 mt-0.5">{stats.dominantEmotion.desc}</p>
                  </div>
                </div>
              ) : (
                <p className="text-sm text-slate-500 mt-4">Belum ada pengeluaran emosional. Pertahankan!</p>
              )}
            </div>

            {stats.dominantEmotion && (
              <div className="mt-4 p-3 bg-slate-950/50 rounded-xl border border-slate-800/80">
                <p className="text-xs text-slate-400">
                  Total dana tersedot emosi ini: <strong className="text-rose-400">Rp {(stats.emotionCounts[stats.dominantEmotion.id] || 0).toLocaleString('id-ID')}</strong>
                </p>
              </div>
            )}
          </div>

        </div>

        {/* MAIN CONTENT GRID */}
        <div className="grid grid-cols-1 lg:grid-cols-12 gap-8">
          
          {/* FORM INPUT SECTION (Left Column) */}
          <div className="lg:col-span-5 bg-slate-900 border border-slate-800 rounded-3xl p-6 h-fit space-y-6">
            <div className="flex items-center gap-2 border-b border-slate-800 pb-4">
              <PlusCircle className="w-5 h-5 text-rose-500" />
              <h2 className="text-lg font-bold text-white">Input Pengeluaran Baru</h2>
            </div>

            <form onSubmit={handleSubmit} className="space-y-4">
              {/* Item Name */}
              <div>
                <label className="block text-xs font-semibold text-slate-400 uppercase tracking-wider mb-2">
                  Nama Barang / Transaksi
                </label>
                <input
                  type="text"
                  placeholder="Misal: Es Kopi Boba Size L"
                  value={title}
                  onChange={(e) => setTitle(e.target.value)}
                  className="w-full bg-slate-950 border border-slate-800 rounded-xl px-4 py-3 text-sm text-white focus:outline-none focus:border-rose-500 transition"
                  required
                />
              </div>

              {/* Amount & Category Grid */}
              <div className="grid grid-cols-1 sm:grid-cols-2 gap-4">
                <div>
                  <label className="block text-xs font-semibold text-slate-400 uppercase tracking-wider mb-2">
                    Nominal (Rp)
                  </label>
                  <input
                    type="number"
                    placeholder="35000"
                    value={amount}
                    onChange={(e) => setAmount(e.target.value)}
                    className="w-full bg-slate-950 border border-slate-800 rounded-xl px-4 py-3 text-sm text-white focus:outline-none focus:border-rose-500 transition"
                    required
                  />
                </div>

                <div>
                  <label className="block text-xs font-semibold text-slate-400 uppercase tracking-wider mb-2">
                    Kategori
                  </label>
                  <select
                    value={category}
                    onChange={(e) => setCategory(e.target.value)}
                    className="w-full bg-slate-950 border border-slate-800 rounded-xl px-3 py-3 text-sm text-white focus:outline-none focus:border-rose-500 transition"
                  >
                    {CATEGORIES.map((cat, idx) => (
                      <option key={idx} value={cat}>{cat}</option>
                    ))}
                  </select>
                </div>
              </div>

              {/* Emotion Selector */}
              <div>
                <label className="block text-xs font-semibold text-slate-400 uppercase tracking-wider mb-2">
                  Emosi Saat Beli (Jujur Ya!)
                </label>
                <div className="grid grid-cols-1 gap-2">
                  {EMOTIONS.map((emo) => {
                    const IconComp = emo.icon;
                    const isSelected = selectedEmotion === emo.id;
                    return (
                      <button
                        key={emo.id}
                        type="button"
                        onClick={() => setSelectedEmotion(emo.id)}
                        className={`flex items-center justify-between p-3 rounded-xl border text-left transition-all ${
                          isSelected 
                            ? `${emo.border} bg-slate-800 ring-1 ring-rose-500/50` 
                            : 'border-slate-800 bg-slate-950/40 hover:bg-slate-800/40'
                        }`}
                      >
                        <div className="flex items-center gap-3">
                          <div className={`p-2 rounded-lg ${emo.color} text-white`}>
                            <IconComp className="w-4 h-4" />
                          </div>
                          <div>
                            <p className="text-sm font-semibold text-slate-200">{emo.label}</p>
                            <p className="text-xs text-slate-500">{emo.desc}</p>
                          </div>
                        </div>
                        <span className={`text-xs px-2 py-0.5 rounded-full font-medium ${
                          emo.impulse ? 'bg-rose-500/10 text-rose-400' : 'bg-emerald-500/10 text-emerald-400'
                        }`}>
                          {emo.impulse ? 'Impulse' : 'Real Need'}
                        </span>
                      </button>
                    );
                  })}
                </div>
              </div>

              {/* Optional Note */}
              <div>
                <label className="block text-xs font-semibold text-slate-400 uppercase tracking-wider mb-2">
                  Catatan / Alasan Dalam Hati (Opsional)
                </label>
                <input
                  type="text"
                  placeholder="Misal: Lagi BM banget gara-gara liat IG story"
                  value={note}
                  onChange={(e) => setNote(e.target.value)}
                  className="w-full bg-slate-950 border border-slate-800 rounded-xl px-4 py-3 text-sm text-white focus:outline-none focus:border-rose-500 transition"
                />
              </div>

              {/* Submit Button */}
              <button
                type="submit"
                className="w-full py-3.5 bg-gradient-to-r from-rose-600 to-amber-600 hover:from-rose-500 hover:to-amber-500 text-white font-bold rounded-xl shadow-lg shadow-rose-600/20 transition transform active:scale-[0.99] flex items-center justify-center gap-2 mt-2"
              >
                <PlusCircle className="w-5 h-5" /> Catat & Evaluasi Emosi
              </button>
            </form>
          </div>

          {/* EXPENSE LIST & FILTER SECTION (Right Column) */}
          <div className="lg:col-span-7 space-y-4">
            
            {/* Filter Bar & Header */}
            <div className="bg-slate-900 border border-slate-800 rounded-2xl p-4 flex flex-col sm:flex-row justify-between items-start sm:items-center gap-4">
              <div className="flex items-center gap-2">
                <PieIcon className="w-5 h-5 text-amber-400" />
                <h3 className="font-bold text-white">Riwayat Pengeluaran</h3>
                <span className="text-xs bg-slate-800 text-slate-400 px-2.5 py-1 rounded-full">
                  {filteredExpenses.length} items
                </span>
              </div>

              {/* Filter dropdown */}
              <div className="flex items-center gap-2 w-full sm:w-auto">
                <Filter className="w-4 h-4 text-slate-400" />
                <select
                  value={filterEmotion}
                  onChange={(e) => setFilterEmotion(e.target.value)}
                  className="bg-slate-950 border border-slate-800 text-slate-300 text-xs rounded-xl px-3 py-2 focus:outline-none focus:border-rose-500 w-full sm:w-auto"
                >
                  <option value="ALL">Semua Emosi</option>
                  {EMOTIONS.map(e => (
                    <option key={e.id} value={e.id}>{e.label}</option>
                  ))}
                </select>
              </div>
            </div>

            {/* Expenses List */}
            <div className="space-y-3">
              {filteredExpenses.length === 0 ? (
                <div className="bg-slate-900/50 border border-dashed border-slate-800 rounded-3xl p-12 text-center">
                  <ShoppingBag className="w-12 h-12 text-slate-600 mx-auto mb-3" />
                  <p className="text-slate-400 font-medium">Belum ada transaksi di kategori ini.</p>
                  <p className="text-xs text-slate-600 mt-1">Coba catat pengeluaran baru lu di form sebelah kiri.</p>
                </div>
              ) : (
                filteredExpenses.map((expense) => {
                  const emoObj = EMOTIONS.find(e => e.id === expense.emotionId) || EMOTIONS[0];
                  const IconComp = emoObj.icon;

                  return (
                    <div 
                      key={expense.id}
                      className="bg-slate-900 border border-slate-800/80 hover:border-slate-700 rounded-2xl p-4 transition flex flex-col sm:flex-row sm:items-center justify-between gap-4 group"
                    >
                      <div className="flex items-start gap-3">
                        <div className={`p-3 rounded-xl shrink-0 ${emoObj.color} text-white mt-1 sm:mt-0`}>
                          <IconComp className="w-5 h-5" />
                        </div>
                        <div>
                          <div className="flex items-center gap-2 flex-wrap">
                            <h4 className="font-semibold text-white">{expense.title}</h4>
                            <span className="text-[10px] bg-slate-800 text-slate-400 px-2 py-0.5 rounded-md">
                              {expense.category}
                            </span>
                          </div>
                          
                          {/* Note & Emotion Tag */}
                          <div className="flex items-center gap-2 mt-1.5 flex-wrap">
                            <span className={`text-xs px-2 py-0.5 rounded-full font-medium ${emoObj.text} ${emoObj.border} border bg-slate-950`}>
                              {emoObj.label}
                            </span>
                            {expense.note && (
                              <p className="text-xs text-slate-400 italic">
                                "{expense.note}"
                              </p>
                            )}
                          </div>
                        </div>
                      </div>

                      {/* Right Amount & Actions */}
                      <div className="flex items-center justify-between sm:justify-end gap-4 border-t sm:border-t-0 pt-3 sm:pt-0 border-slate-800/60">
                        <div className="text-left sm:text-right">
                          <p className="font-extrabold text-slate-100">
                            Rp {expense.amount.toLocaleString('id-ID')}
                          </p>
                          <p className="text-[10px] text-slate-500">{expense.date}</p>
                        </div>
                        
                        <button
                          onClick={() => handleDelete(expense.id)}
                          className="p-2 text-slate-500 hover:text-rose-400 hover:bg-rose-500/10 rounded-xl transition opacity-80 sm:opacity-0 sm:group-hover:opacity-100"
                          title="Hapus Catatan"
                        >
                          <Trash2 className="w-4 h-4" />
                        </button>
                      </div>
                    </div>
                  );
                })
              )}
            </div>

          </div>

        </div>

      </div>
    </div>
  );
}
