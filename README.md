import React, { useState } from 'react';
import { Calendar, Users, Lightbulb, ClipboardCheck, ArrowRight, FileText, Award, Globe, MessageCircle, Youtube, Facebook, Instagram, ScanLine } from 'lucide-react';

const PortalOpsiYPS = () => {
  const [activeTab, setActiveTab] = useState('home');

  // Smooth scroll function
  const scrollToSection = (id) => {
    const element = document.getElementById(id);
    if (element) {
      element.scrollIntoView({ behavior: 'smooth' });
    }
    setActiveTab(id);
  };

  // Branding Colors YPS
  const colors = {
    forestGreen: '#049229',
    darkGreen: '#03671D',
    gold: '#ffd700',
    pumpkin: '#FF6700',
    white: '#ffffff',
    black: '#000000'
  };

  return (
    <div className="min-h-screen bg-gray-50 font-sans text-gray-800">
      {/* Navigation */}
      <nav className="fixed top-0 w-full bg-white shadow-md z-50">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="flex justify-between h-16 items-center">
            <div className="flex-shrink-0 flex items-center">
              {/* Logo text using YPS Colors */}
              <span className="font-bold text-xl md:text-2xl" style={{ color: colors.forestGreen }}>
                OPSI <span style={{ color: colors.pumpkin }}>SMP YPS SINGKOLE</span>
              </span>
            </div>
            <div className="hidden md:flex space-x-8">
              <button onClick={() => scrollToSection('home')} className="text-gray-700 hover:text-[#049229] font-medium transition-colors">Beranda</button>
              <button onClick={() => scrollToSection('timeline')} className="text-gray-700 hover:text-[#049229] font-medium transition-colors">Roadmap</button>
              <button onClick={() => scrollToSection('info')} className="text-gray-700 hover:text-[#049229] font-medium transition-colors">Pusat Informasi</button>
            </div>
            <div>
              <button 
                onClick={() => window.open('https://bit.ly/tim-opsi-smpyps-2026', '_blank')}
                className="text-white px-5 py-2 rounded-full font-bold transition shadow-lg transform hover:scale-105"
                style={{ backgroundColor: colors.forestGreen }}
              >
                Daftar Sekarang
              </button>
            </div>
          </div>
        </div>
      </nav>

      {/* Hero Section */}
      <div id="home" className="pt-24 pb-16 text-white" style={{ background: `linear-gradient(135deg, ${colors.forestGreen} 0%, ${colors.darkGreen} 100%)` }}>
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col md:flex-row items-center">
          
          {/* Left Content */}
          <div className="md:w-3/5 mb-10 md:mb-0 pr-0 md:pr-10">
            <div className="inline-block text-white px-3 py-1 rounded-full text-sm font-bold mb-4 animate-pulse" style={{ backgroundColor: colors.pumpkin }}>
              Seleksi Tim Sekolah 2026
            </div>
            <h1 className="text-3xl md:text-5xl font-extrabold leading-tight mb-4">
              Siap Jadi Tim OPSI <br/>
              SMP YPS Singkole 2026?
            </h1>
            <div className="w-20 h-1 bg-[#ffd700] mb-6"></div> {/* Gold underline */}
            <p className="text-lg md:text-xl mb-2 text-green-50 font-medium">
              Tema:
            </p>
            <p className="text-xl md:text-2xl mb-8 font-bold italic text-white">
              "Menjadi Peneliti Muda yang <span style={{ color: colors.gold }}>Tangguh</span>, <span style={{ color: colors.gold }}>Mandiri</span>, dan <span style={{ color: colors.gold }}>Beretika</span>"
            </p>
            
            <div className="flex flex-col sm:flex-row space-y-4 sm:space-y-0 sm:space-x-4">
              <button 
                onClick={() => window.open('https://bit.ly/tim-opsi-smpyps-2026', '_blank')}
                className="bg-white text-[#049229] px-8 py-3 rounded-lg font-bold shadow-lg hover:bg-gray-100 transition flex items-center justify-center"
              >
                Daftar via Link <ArrowRight className="ml-2 w-5 h-5"/>
              </button>
              <button onClick={() => scrollToSection('timeline')} className="border-2 border-white text-white px-8 py-3 rounded-lg font-bold hover:bg-white hover:text-[#049229] transition flex items-center justify-center">
                Lihat Jadwal
              </button>
            </div>
          </div>

          {/* Right Content - QR Code Card */}
          <div className="md:w-2/5 flex justify-center md:justify-end">
             <div className="relative bg-white p-6 rounded-2xl shadow-2xl text-gray-800 max-w-sm w-full transform rotate-1 hover:rotate-0 transition duration-300">
                <div className="absolute -top-3 -right-3 w-10 h-10 rounded-full flex items-center justify-center text-white shadow" style={{ backgroundColor: colors.pumpkin }}>
                    <ScanLine className="w-5 h-5" />
                </div>
                
                <div className="text-center mb-4">
                    <h3 className="font-bold text-xl text-[#049229]">Scan untuk Daftar</h3>
                    <p className="text-sm text-gray-500">Arahkan kamera HP Anda ke sini</p>
                </div>

                <div className="bg-gray-100 p-4 rounded-xl border-2 border-dashed border-gray-300 mb-4 flex justify-center items-center">
                    {/* QR Code */}
                    <img 
                        src="https://api.qrserver.com/v1/create-qr-code/?size=180x180&data=https://bit.ly/tim-opsi-smpyps-2026" 
                        alt="QR Code Pendaftaran" 
                        className="w-48 h-48 object-contain"
                    />
                </div>

                <div className="text-center">
                    <p className="text-xs font-mono bg-gray-100 py-2 px-3 rounded text-gray-600 truncate">
                        https://bit.ly/tim-opsi-smpyps-2026
                    </p>
                </div>
             </div>
          </div>
        </div>
      </div>

      {/* Fields Section */}
      <div className="py-16 bg-white">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
          <h2 className="text-3xl font-bold text-gray-900 mb-12">Bidang Kompetisi</h2>
          <div className="grid md:grid-cols-3 gap-8">
            {/* Card 1 - IPA */}
            <div className="p-8 rounded-xl bg-green-50 border border-green-100 hover:shadow-xl transition duration-300 transform hover:-translate-y-2">
              <div className="w-16 h-16 rounded-full flex items-center justify-center mx-auto mb-6 text-white shadow-lg" style={{ backgroundColor: colors.forestGreen }}>
                <span className="text-3xl">🌱</span>
              </div>
              <h3 className="text-xl font-bold text-gray-900 mb-3">IPA</h3>
              <p className="text-gray-600 text-sm leading-relaxed">Sains Alam & Lingkungan. Meneliti gejala alam, biologi, fisika, dan kualitas lingkungan sekitar.</p>
            </div>
            {/* Card 2 - IPS */}
            <div className="p-8 rounded-xl bg-yellow-50 border border-yellow-100 hover:shadow-xl transition duration-300 transform hover:-translate-y-2">
              <div className="w-16 h-16 rounded-full flex items-center justify-center mx-auto mb-6 text-white shadow-lg" style={{ backgroundColor: colors.gold }}>
                <span className="text-3xl">👥</span>
              </div>
              <h3 className="text-xl font-bold text-gray-900 mb-3">IPS</h3>
              <p className="text-gray-600 text-sm leading-relaxed">Sosial & Humaniora. Meneliti perilaku manusia, budaya, sejarah lokal, dan interaksi sosial.</p>
            </div>
            {/* Card 3 - IPT */}
            <div className="p-8 rounded-xl bg-orange-50 border border-orange-100 hover:shadow-xl transition duration-300 transform hover:-translate-y-2">
              <div className="w-16 h-16 rounded-full flex items-center justify-center mx-auto mb-6 text-white shadow-lg" style={{ backgroundColor: colors.pumpkin }}>
                <span className="text-3xl">⚙️</span>
              </div>
              <h3 className="text-xl font-bold text-gray-900 mb-3">IPT</h3>
              <p className="text-gray-600 text-sm leading-relaxed">Ilmu Pengetahuan Terapan. Rekayasa teknologi, pembuatan alat, dan inovasi produk.</p>
            </div>
          </div>
        </div>
      </div>

      {/* Timeline Section */}
      <div id="timeline" className="py-16 bg-gray-50">
        <div className="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
          <h2 className="text-3xl font-bold text-center text-gray-900 mb-12">Roadmap Menuju Nasional</h2>
          
          <div className="relative">
            {/* Vertical Line */}
            <div className="absolute left-1/2 transform -translate-x-1/2 w-1 h-full bg-gray-200"></div>

            {/* Timeline Item 1 */}
            <div className="relative flex items-center justify-between mb-12">
              <div className="w-5/12 text-right pr-8">
                <h4 className="text-xl font-bold" style={{ color: colors.forestGreen }}>Pendaftaran & Komitmen</h4>
                <p className="text-gray-600 mt-2 text-sm">Isi form & tanda tangani Pakta Integritas.</p>
              </div>
              <div className="absolute left-1/2 transform -translate-x-1/2 w-6 h-6 rounded-full border-4 border-white shadow bg-[#049229]"></div>
              <div className="w-5/12 pl-8">
                <span className="inline-block px-3 py-1 rounded-full text-xs font-bold text-white shadow-sm" style={{ backgroundColor: colors.forestGreen }}>01 - 08 Jan 2026</span>
              </div>
            </div>

            {/* Timeline Item 2 */}
            <div className="relative flex items-center justify-between mb-12">
              <div className="w-5/12 text-right pr-8">
                 <span className="inline-block px-3 py-1 rounded-full text-xs font-bold text-white shadow-sm" style={{ backgroundColor: colors.pumpkin }}>09 Jan 2026</span>
              </div>
              <div className="absolute left-1/2 transform -translate-x-1/2 w-6 h-6 rounded-full border-4 border-white shadow bg-[#FF6700]"></div>
              <div className="w-5/12 pl-8">
                <h4 className="text-xl font-bold text-gray-900">Workshop Canvas</h4>
                <p className="text-gray-600 mt-2 text-sm">Pelatihan Value Proposition & Business Model Canvas.</p>
              </div>
            </div>

            {/* Timeline Item 3 - IMPORTANT */}
            <div className="relative flex items-center justify-between mb-12">
              <div className="w-5/12 text-right pr-8">
                <h4 className="text-xl font-bold" style={{ color: colors.forestGreen }}>Inkubasi & Validasi Ide</h4>
                <p className="text-gray-600 mt-2 text-sm">Observasi lapangan dan penyusunan ide mandiri.</p>
                <div className="mt-2 bg-red-100 text-red-800 p-2 rounded text-xs font-bold inline-block border border-red-200">
                    DEADLINE: 03 FEB 2026
                </div>
              </div>
              <div className="absolute left-1/2 transform -translate-x-1/2 w-8 h-8 bg-white border-4 rounded-full shadow flex items-center justify-center z-10" style={{ borderColor: colors.forestGreen }}>
                 <div className="w-3 h-3 rounded-full" style={{ backgroundColor: colors.forestGreen }}></div>
              </div>
              <div className="w-5/12 pl-8">
                <span className="inline-block px-3 py-1 rounded-full text-xs font-bold text-white shadow-sm" style={{ backgroundColor: colors.forestGreen }}>10 Jan - 03 Feb 2026</span>
              </div>
            </div>

             {/* Timeline Item 4 */}
             <div className="relative flex items-center justify-between mb-12">
              <div className="w-5/12 text-right pr-8">
                 <span className="inline-block px-3 py-1 rounded-full text-xs font-bold text-white shadow-sm" style={{ backgroundColor: colors.forestGreen }}>06 Feb 2026</span>
              </div>
              <div className="absolute left-1/2 transform -translate-x-1/2 w-6 h-6 rounded-full border-4 border-white shadow bg-[#049229]"></div>
              <div className="w-5/12 pl-8">
                <h4 className="text-xl font-bold text-gray-900">Selection Day</h4>
                <p className="text-gray-600 mt-2 text-sm">Presentasi ide di hadapan guru.</p>
              </div>
            </div>

             {/* Timeline Item 5 */}
             <div className="relative flex items-center justify-between mb-12">
              <div className="w-5/12 text-right pr-8">
                <h4 className="text-xl font-bold" style={{ color: colors.pumpkin }}>Pengumuman & SK</h4>
                <p className="text-gray-600 mt-2 text-sm">Penetapan Tim Delegasi Sekolah.</p>
              </div>
              <div className="absolute left-1/2 transform -translate-x-1/2 w-6 h-6 rounded-full border-4 border-white shadow bg-[#FF6700]"></div>
              <div className="w-5/12 pl-8">
                <span className="inline-block px-3 py-1 rounded-full text-xs font-bold text-white shadow-sm" style={{ backgroundColor: colors.pumpkin }}>10 Feb 2026</span>
              </div>
            </div>

             {/* Timeline Item 6 */}
             <div className="relative flex items-center justify-between">
              <div className="w-5/12 text-right pr-8">
                 <span className="inline-block px-3 py-1 rounded-full text-xs font-bold text-gray-800 shadow-sm" style={{ backgroundColor: colors.gold }}>16 Feb - 31 Mar 2026</span>
              </div>
              <div className="absolute left-1/2 transform -translate-x-1/2 w-6 h-6 rounded-full border-4 border-white shadow bg-[#ffd700]"></div>
              <div className="w-5/12 pl-8">
                <h4 className="text-xl font-bold text-gray-900">Klinik Proposal</h4>
                <p className="text-gray-600 mt-2 text-sm">Penulisan Bab 1-3 Intensif & Submit Nasional.</p>
              </div>
            </div>

          </div>
        </div>
      </div>

      {/* Canvas Explanation */}
      <div className="py-16 bg-white border-t">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div className="rounded-2xl p-8 md:p-12 text-white flex flex-col md:flex-row items-center justify-between shadow-2xl relative overflow-hidden" style={{ backgroundColor: colors.forestGreen }}>
                {/* Background Pattern Overlay */}
                <div className="absolute top-0 right-0 w-64 h-64 bg-white opacity-5 rounded-full -mr-20 -mt-20"></div>
                <div className="absolute bottom-0 left-0 w-40 h-40 bg-white opacity-5 rounded-full -ml-10 -mb-10"></div>
                
                <div className="md:w-2/3 relative z-10">
                    <h2 className="text-3xl font-bold mb-4">Mengapa Pakai "Canvas"?</h2>
                    <p className="text-lg mb-6 opacity-90">
                        Kami tidak ingin kalian hanya meneliti, tapi <strong>berinovasi</strong>.
                        Metode <em>Value Proposition Canvas (VPC)</em> dan <em>Business Model Canvas (BMC)</em> membantu kalian memastikan ide kalian benar-benar dibutuhkan dan bisa diterapkan.
                    </p>
                    <div className="flex flex-wrap gap-4">
                        <div className="bg-white/10 px-4 py-2 rounded-lg border border-white/20 backdrop-blur-sm">
                            💡 Orisinalitas
                        </div>
                        <div className="bg-white/10 px-4 py-2 rounded-lg border border-white/20 backdrop-blur-sm">
                            🎯 Tepat Sasaran
                        </div>
                        <div className="bg-white/10 px-4 py-2 rounded-lg border border-white/20 backdrop-blur-sm">
                            📝 Terstruktur
                        </div>
                    </div>
                </div>
                <div className="md:w-1/3 mt-8 md:mt-0 flex justify-center relative z-10">
                    <div className="bg-white/20 p-4 rounded-full">
                        <FileText className="w-24 h-24 text-white" />
                    </div>
                </div>
            </div>
        </div>
      </div>

      {/* Pusat Informasi Section */}
      <div id="info" className="py-16 bg-gray-900 text-gray-300">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div className="text-center mb-12">
                <h2 className="text-3xl font-bold text-white mb-4">Pusat Informasi</h2>
                <p className="text-gray-400">Ikuti perkembangan terbaru melalui kanal resmi kami.</p>
            </div>
            
            <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                {/* Social Media Card */}
                <div className="bg-gray-800 p-8 rounded-xl border-t-4" style={{ borderColor: colors.pumpkin }}>
                    <div className="flex items-center mb-6">
                        <Users className="w-8 h-8 mr-3" style={{ color: colors.pumpkin }}/>
                        <h4 className="text-xl font-bold text-white">Media Sosial</h4>
                    </div>
                    <div className="space-y-4">
                        <div className="flex items-center text-gray-300">
                            <Instagram className="w-5 h-5 mr-3 text-pink-500"/>
                            <span>SMP YPS Singkole</span>
                        </div>
                        <div className="flex items-center text-gray-300">
                            <Facebook className="w-5 h-5 mr-3 text-blue-600"/>
                            <span>SMP YPS Singkole</span>
                        </div>
                        <div className="flex items-center text-gray-300">
                            <Youtube className="w-5 h-5 mr-3 text-red-600"/>
                            <span>SMP YPS Singkole</span>
                        </div>
                    </div>
                </div>

                {/* Website Card */}
                <div className="bg-gray-800 p-8 rounded-xl hover:bg-gray-700 transition border-t-4" style={{ borderColor: colors.forestGreen }}>
                    <div className="flex items-center mb-6">
                        <Globe className="w-8 h-8 mr-3" style={{ color: colors.forestGreen }}/>
                        <h4 className="text-xl font-bold text-white">Website Sekolah</h4>
                    </div>
                    <p className="text-sm text-gray-400 mb-6">Kunjungi website resmi sekolah untuk informasi akademik lainnya.</p>
                    <a href="https://smp.yps.sch.id" target="_blank" rel="noreferrer" className="inline-flex items-center font-bold hover:underline" style={{ color: colors.forestGreen }}>
                        smp.yps.sch.id <ArrowRight className="w-4 h-4 ml-2"/>
                    </a>
                </div>

                {/* Contact Person Card */}
                <div className="bg-gray-800 p-8 rounded-xl hover:bg-gray-700 transition border-t-4" style={{ borderColor: colors.gold }}>
                    <div className="flex items-center mb-6">
                        <MessageCircle className="w-8 h-8 mr-3" style={{ color: colors.gold }}/>
                        <h4 className="text-xl font-bold text-white">Hubungi Pembina</h4>
                    </div>
                    <p className="text-sm text-gray-400 mb-2">Punya pertanyaan seputar seleksi OPSI?</p>
                    <div className="bg-gray-900 p-4 rounded-lg mt-4 border border-gray-700">
                        <p className="font-bold text-white">Faisal, S.Si</p>
                        <p className="text-xs text-gray-400 mt-1">Koordinator KIR</p>
                        <a 
                            href="mailto:faisal@yps.sch.id" 
                            className="mt-3 block text-center text-white text-sm py-2 rounded transition hover:opacity-90"
                            style={{ backgroundColor: colors.forestGreen }}
                        >
                            Chat via Google Chat
                        </a>
                    </div>
                </div>
            </div>
        </div>
      </div>

      {/* Footer */}
      <footer className="bg-black text-white py-8 border-t border-gray-800">
        <div className="max-w-7xl mx-auto px-4 text-center">
            <p className="font-bold text-xl mb-2" style={{ color: colors.gold }}>Tim OPSI SMP YPS Singkole</p>
            <p className="text-gray-400 text-sm mb-4">Membangun Budaya Riset Sejak Dini</p>
            <div className="flex justify-center space-x-4 mb-4">
                <div className="h-1 w-12 rounded" style={{ backgroundColor: colors.forestGreen }}></div>
                <div className="h-1 w-12 rounded" style={{ backgroundColor: colors.gold }}></div>
                <div className="h-1 w-12 rounded" style={{ backgroundColor: colors.pumpkin }}></div>
            </div>
            <p className="text-xs text-gray-600">&copy; 2026 SMP YPS Singkole. All rights reserved.</p>
        </div>
      </footer>
    </div>
  );
};

export default PortalOpsiYPS;
