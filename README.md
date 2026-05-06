# BMWMotors
import React, { useState, useEffect } from 'react';
import { 
  Car, 
  Battery, 
  Cpu, 
  Globe, 
  Zap, 
  Target, 
  Users, 
  TrendingUp, 
  ChevronRight, 
  Menu, 
  X,
  PlayCircle,
  Leaf,
  ShieldCheck
} from 'lucide-react';

// Date pentru Pilonii Strategici
const strategicPillars = [
  {
    id: 0,
    title: "Electrificare Inteligentă",
    icon: <Battery className="w-8 h-8 mb-4 text-blue-500" />,
    description: "Tranziția accelerată către o flotă 100% electrică, optimizând arhitectura Neue Klasse pentru a oferi cu 30% mai multă autonomie și încărcare ultra-rapidă, fără a compromite 'Plăcerea de a conduce'.",
    metric: "100% Electric până în 2035"
  },
  {
    id: 1,
    title: "Ecosistem Digital & AI",
    icon: <Cpu className="w-8 h-8 mb-4 text-blue-500" />,
    description: "Transformarea mașinii din mijloc de transport în 'Ultimate Digital Companion'. Integrarea inteligenței artificiale predictive pentru personalizarea extremă a experienței șoferului și condus autonom Nivel 4.",
    metric: "50M+ Vehicule Conectate"
  },
  {
    id: 2,
    title: "Economie Circulară",
    icon: <Globe className="w-8 h-8 mb-4 text-blue-500" />,
    description: "Implementarea conceptului 'Secondary First'. Vom folosi materiale reciclate în proporție de 50% pentru noile modele și vom asigura un lanț de aprovizionare complet transparent și etic, cu zero emisii de carbon.",
    metric: "Net Zero Carbon 2050"
  },
  {
    id: 3,
    title: "Experiența Clientului 3.0",
    icon: <Users className="w-8 h-8 mb-4 text-blue-500" />,
    description: "Revoluționarea modului în care clienții interacționează cu brandul. De la showroom-uri în realitate virtuală (Metaverse) până la servicii de mentenanță predictive direct la domiciliu.",
    metric: "99% Rata de Fidelizare"
  }
];

// Date pentru Roadmap
const roadmapSteps = [
  { year: "Anul 1", title: "Fundația Agilă", desc: "Optimizarea lanțului de aprovizionare prin AI și lansarea noii interfețe digitale iDrive X." },
  { year: "Anul 2", title: "Expansiunea Neue Klasse", desc: "Lansarea a 3 noi modele bazate pe arhitectura Neue Klasse în segmentele de volum." },
  { year: "Anul 3", title: "Sustenabilitate Activă", desc: "Atingerea pragului de 30% materiale reciclate în toată producția globală." },
  { year: "Anul 4", title: "Autonomie Avansată", desc: "Lansarea pachetului comercial de condus autonom Nivel 4 în marile orașe europene." },
  { year: "Anul 5", title: "Lider de Piață", desc: "Dominanță globală în segmentul premium electric și cel mai mare scor NPS din industrie." }
];

export default function BMWVisionPitch() {
  const [activeTab, setActiveTab] = useState(0);
  const [isMenuOpen, setIsMenuOpen] = useState(false);
  const [isScrolled, setIsScrolled] = useState(false);
  const [aiAdoption, setAiAdoption] = useState(50);

  // Efect pentru scroll navbar
  useEffect(() => {
    const handleScroll = () => {
      setIsScrolled(window.scrollY > 50);
    };
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  }, []);

  return (
    <div className="min-h-screen bg-slate-50 font-sans text-slate-900 selection:bg-blue-200">
      
      {/* Navigation */}
      <nav className={`fixed w-full z-50 transition-all duration-300 ${isScrolled ? 'bg-white shadow-md py-3' : 'bg-transparent py-5'}`}>
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex justify-between items-center">
          <div className="flex items-center space-x-2">
            {/* Logo Placeholder (using icons to represent the brand subtly) */}
            <div className="w-10 h-10 rounded-full bg-gradient-to-br from-blue-600 to-sky-400 flex items-center justify-center text-white font-bold text-xl shadow-lg">
              B
            </div>
            <span className={`text-xl font-bold tracking-tight ${isScrolled ? 'text-slate-900' : 'text-slate-900 lg:text-white drop-shadow-md'}`}>
              Vision 2030
            </span>
          </div>
          
          <div className="hidden md:flex space-x-8">
            <a href="#viziune" className={`text-sm font-semibold uppercase tracking-wider hover:text-blue-600 transition-colors ${isScrolled ? 'text-slate-600' : 'text-slate-200 hover:text-white'}`}>Viziune</a>
            <a href="#strategie" className={`text-sm font-semibold uppercase tracking-wider hover:text-blue-600 transition-colors ${isScrolled ? 'text-slate-600' : 'text-slate-200 hover:text-white'}`}>Strategie</a>
            <a href="#simulator" className={`text-sm font-semibold uppercase tracking-wider hover:text-blue-600 transition-colors ${isScrolled ? 'text-slate-600' : 'text-slate-200 hover:text-white'}`}>Simulator AI</a>
            <a href="#roadmap" className={`text-sm font-semibold uppercase tracking-wider hover:text-blue-600 transition-colors ${isScrolled ? 'text-slate-600' : 'text-slate-200 hover:text-white'}`}>Roadmap</a>
          </div>

          <div className="md:hidden">
            <button onClick={() => setIsMenuOpen(!isMenuOpen)} className={isScrolled ? 'text-slate-900' : 'text-white'}>
              {isMenuOpen ? <X /> : <Menu />}
            </button>
          </div>
        </div>
      </nav>

      {/* Mobile Menu */}
      {isMenuOpen && (
        <div className="fixed inset-0 z-40 bg-white pt-20 px-4">
          <div className="flex flex-col space-y-6 text-xl font-medium">
            <a href="#viziune" onClick={() => setIsMenuOpen(false)} className="border-b pb-2">Viziune</a>
            <a href="#strategie" onClick={() => setIsMenuOpen(false)} className="border-b pb-2">Strategie</a>
            <a href="#simulator" onClick={() => setIsMenuOpen(false)} className="border-b pb-2">Simulator AI</a>
            <a href="#roadmap" onClick={() => setIsMenuOpen(false)} className="border-b pb-2">Roadmap</a>
          </div>
        </div>
      )}

      {/* Hero Section */}
      <section id="viziune" className="relative h-screen flex items-center justify-center overflow-hidden">
        <div className="absolute inset-0 bg-slate-900">
          <div className="absolute inset-0 opacity-40 bg-[radial-gradient(circle_at_center,_var(--tw-gradient-stops))] from-blue-900 via-slate-900 to-black"></div>
          {/* Abstract background elements */}
          <div className="absolute top-1/4 left-1/4 w-96 h-96 bg-blue-600 rounded-full mix-blend-multiply filter blur-[128px] opacity-50 animate-pulse"></div>
          <div className="absolute bottom-1/4 right-1/4 w-96 h-96 bg-sky-400 rounded-full mix-blend-multiply filter blur-[128px] opacity-30"></div>
        </div>
        
        <div className="relative z-10 text-center px-4 max-w-4xl mx-auto mt-20">
          <span className="inline-block py-1 px-3 rounded-full bg-blue-500/20 text-blue-300 text-sm font-semibold tracking-widest uppercase mb-6 border border-blue-500/30">
            Propunere Management Executiv
          </span>
          <h1 className="text-5xl md:text-7xl font-extrabold text-white mb-6 leading-tight tracking-tighter">
            Redefinim <span className="text-transparent bg-clip-text bg-gradient-to-r from-blue-400 to-sky-300">Viitorul</span> Mobilității
          </h1>
          <p className="text-xl md:text-2xl text-slate-300 mb-10 font-light max-w-3xl mx-auto">
            O viziune strategică pentru BMW Motors axată pe inovație digitală, sustenabilitate circulară și performanță pură.
          </p>
          <div className="flex flex-col sm:flex-row justify-center gap-4">
            <a href="#strategie" className="px-8 py-4 bg-white text-slate-900 font-bold rounded-full hover:bg-slate-100 transition-all transform hover:scale-105 shadow-lg flex items-center justify-center">
              Descopera Strategia <ChevronRight className="ml-2 w-5 h-5" />
            </a>
          </div>
        </div>
      </section>

      {/* Philosophy / Piloni Strategici */}
      <section id="strategie" className="py-24 bg-white">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="text-center mb-16">
            <h2 className="text-3xl md:text-5xl font-bold text-slate-900 mb-4 tracking-tight">Cei 4 Piloni ai Succesului</h2>
            <p className="text-lg text-slate-600 max-w-2xl mx-auto">
              Strategia mea de management se bazează pe transformarea fundamentală a modelului de business, păstrând în același timp ADN-ul inconfundabil BMW.
            </p>
          </div>

          {/* Interactive Tabs */}
          <div className="flex flex-wrap justify-center gap-2 md:gap-4 mb-12">
            {strategicPillars.map((pillar, index) => (
              <button
                key={pillar.id}
                onClick={() => setActiveTab(index)}
                className={`px-6 py-3 rounded-full text-sm md:text-base font-semibold transition-all duration-300 ${
                  activeTab === index 
                    ? 'bg-blue-600 text-white shadow-md scale-105' 
                    : 'bg-slate-100 text-slate-600 hover:bg-slate-200'
                }`}
              >
                {pillar.title}
              </button>
            ))}
          </div>

          {/* Tab Content */}
          <div className="bg-slate-50 rounded-3xl p-8 md:p-12 shadow-xl border border-slate-100 transition-all duration-500 min-h-[300px] flex items-center">
            <div className="grid md:grid-cols-2 gap-12 items-center">
              <div>
                <div className="inline-block p-4 bg-white rounded-2xl shadow-sm mb-6">
                  {strategicPillars[activeTab].icon}
                </div>
                <h3 className="text-3xl font-bold text-slate-900 mb-4">{strategicPillars[activeTab].title}</h3>
                <p className="text-lg text-slate-600 mb-8 leading-relaxed">
                  {strategicPillars[activeTab].description}
                </p>
                <div className="flex items-center text-blue-600 font-bold bg-blue-50 py-2 px-4 rounded-lg inline-flex">
                  <Target className="w-5 h-5 mr-2" />
                  Obiectiv: {strategicPillars[activeTab].metric}
                </div>
              </div>
              <div className="hidden md:flex justify-center relative">
                {/* Visual representation based on active tab */}
                <div className="w-full h-80 bg-slate-200 rounded-2xl overflow-hidden relative group">
                  <div className="absolute inset-0 bg-gradient-to-tr from-slate-800 to-slate-400 opacity-20 group-hover:opacity-10 transition-opacity"></div>
                  {activeTab === 0 && <div className="w-full h-full bg-gradient-to-br from-blue-100 to-blue-50 flex items-center justify-center text-blue-600"><Battery size={120} opacity={0.2} /></div>}
                  {activeTab === 1 && <div className="w-full h-full bg-gradient-to-br from-indigo-100 to-purple-50 flex items-center justify-center text-indigo-600"><Cpu size={120} opacity={0.2} /></div>}
                  {activeTab === 2 && <div className="w-full h-full bg-gradient-to-br from-emerald-100 to-teal-50 flex items-center justify-center text-emerald-600"><Leaf size={120} opacity={0.2} /></div>}
                  {activeTab === 3 && <div className="w-full h-full bg-gradient-to-br from-orange-100 to-amber-50 flex items-center justify-center text-orange-600"><Users size={120} opacity={0.2} /></div>}
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Interactive Simulator Section */}
      <section id="simulator" className="py-24 bg-slate-900 text-white">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="grid lg:grid-cols-2 gap-16 items-center">
            <div>
              <span className="text-blue-400 font-semibold tracking-wider uppercase text-sm mb-2 block">Viziune Interactivă</span>
              <h2 className="text-3xl md:text-5xl font-bold mb-6">Simulator de Performanță: Impactul Inteligenței Artificiale</h2>
              <p className="text-slate-300 text-lg mb-8 leading-relaxed">
                Ca manager, propun o integrare masivă a AI-ului nu doar în vehicule, ci în întregul lanț de producție și vânzări. Experimentați mai jos impactul estimat al adoptării AI asupra metricilor cheie BMW.
              </p>
              
              <div className="bg-slate-800 p-6 rounded-2xl border border-slate-700 mb-8">
                <label className="flex justify-between text-sm font-medium mb-4">
                  <span>Grad de Adoptare AI în Operațiuni</span>
                  <span className="text-blue-400 font-bold">{aiAdoption}%</span>
                </label>
                <input 
                  type="range" 
                  min="0" 
                  max="100" 
                  value={aiAdoption} 
                  onChange={(e) => setAiAdoption(parseInt(e.target.value))}
                  className="w-full h-2 bg-slate-700 rounded-lg appearance-none cursor-pointer accent-blue-500"
                />
                <div className="flex justify-between text-xs text-slate-500 mt-2">
                  <span>Tradițional</span>
                  <span>Ecosistem Complet AI</span>
                </div>
              </div>
            </div>

            <div className="grid grid-cols-1 sm:grid-cols-2 gap-6">
              {/* Metric Card 1 */}
              <div className="bg-slate-800 p-6 rounded-2xl border border-slate-700 transform transition-transform hover:-translate-y-2">
                <TrendingUp className="w-8 h-8 text-emerald-400 mb-4" />
                <h4 className="text-slate-400 text-sm font-medium mb-1">Eficiență Operațională</h4>
                <div className="text-4xl font-bold text-white mb-2">
                  +{Math.round(aiAdoption * 0.45)}<span className="text-xl text-emerald-400">%</span>
                </div>
                <p className="text-xs text-slate-500">Reducerea timpului de producție și optimizarea logisticii.</p>
              </div>

              {/* Metric Card 2 */}
              <div className="bg-slate-800 p-6 rounded-2xl border border-slate-700 transform transition-transform hover:-translate-y-2">
                <Leaf className="w-8 h-8 text-emerald-400 mb-4" />
                <h4 className="text-slate-400 text-sm font-medium mb-1">Reducere Emisii CO2</h4>
                <div className="text-4xl font-bold text-white mb-2">
                  -{Math.round(aiAdoption * 0.6)}<span className="text-xl text-emerald-400">%</span>
                </div>
                <p className="text-xs text-slate-500">Prin rute logistice inteligente și managementul energiei.</p>
              </div>

              {/* Metric Card 3 */}
              <div className="bg-slate-800 p-6 rounded-2xl border border-slate-700 transform transition-transform hover:-translate-y-2 sm:col-span-2">
                <ShieldCheck className="w-8 h-8 text-blue-400 mb-4" />
                <h4 className="text-slate-400 text-sm font-medium mb-1">Creștere Venituri din Servicii Digitale</h4>
                <div className="flex items-end gap-2 mb-2">
                  <div className="text-4xl font-bold text-white">
                    {Math.round(2 + (aiAdoption * 0.15))}
                  </div>
                  <div className="text-xl text-blue-400 pb-1">Miliarde €</div>
                </div>
                
                {/* Visual Bar */}
                <div className="w-full h-3 bg-slate-700 rounded-full mt-4 overflow-hidden">
                  <div 
                    className="h-full bg-gradient-to-r from-blue-600 to-sky-400 transition-all duration-300"
                    style={{ width: `${Math.min(100, (2 + (aiAdoption * 0.15)) / 17 * 100)}%` }}
                  ></div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Roadmap Section */}
      <section id="roadmap" className="py-24 bg-slate-50">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="text-center mb-16">
            <h2 className="text-3xl md:text-5xl font-bold text-slate-900 mb-4 tracking-tight">Planul de Acțiune (Pe 5 Ani)</h2>
            <p className="text-lg text-slate-600 max-w-2xl mx-auto">
              O tranziție lină necesită execuție impecabilă. Iată pașii strategici pentru consolidarea poziției de lider a companiei BMW.
            </p>
          </div>

          <div className="relative">
            {/* Connecting line */}
            <div className="absolute left-4 md:left-1/2 top-0 bottom-0 w-1 bg-blue-200 transform md:-translate-x-1/2"></div>
            
            <div className="space-y-12">
              {roadmapSteps.map((step, index) => (
                <div key={index} className={`relative flex flex-col md:flex-row items-center ${index % 2 === 0 ? 'md:flex-row-reverse' : ''}`}>
                  {/* Timeline Dot */}
                  <div className="absolute left-4 md:left-1/2 w-8 h-8 bg-blue-600 rounded-full border-4 border-white shadow-md transform -translate-x-1/2 flex items-center justify-center z-10">
                    <div className="w-2 h-2 bg-white rounded-full"></div>
                  </div>
                  
                  {/* Content Box */}
                  <div className="w-full md:w-1/2 pl-12 md:pl-0">
                    <div className={`bg-white p-6 rounded-2xl shadow-sm border border-slate-100 hover:shadow-md transition-shadow ${index % 2 === 0 ? 'md:ml-12' : 'md:mr-12'}`}>
                      <span className="text-blue-600 font-bold text-sm tracking-widest uppercase mb-2 block">{step.year}</span>
                      <h4 className="text-xl font-bold text-slate-900 mb-2">{step.title}</h4>
                      <p className="text-slate-600">{step.desc}</p>
                    </div>
                  </div>
                </div>
              ))}
            </div>
          </div>
        </div>
      </section>

      {/* Call to Action / Conclusion */}
      <section className="py-20 bg-blue-600 text-white text-center">
        <div className="max-w-4xl mx-auto px-4">
          <h2 className="text-3xl md:text-4xl font-bold mb-6">Pregătit să Conduc Tranziția</h2>
          <p className="text-xl text-blue-100 mb-10 font-light">
            BMW nu construiește doar mașini, creează emoție. Cu o viziune clară asupra digitalizării și sustenabilității, sunt pregătit să conduc această companie legendară către cel mai de succes capitol din istoria sa.
          </p>
          <button className="px-8 py-4 bg-slate-900 text-white font-bold rounded-full hover:bg-black transition-colors shadow-xl">
            Programează Interviul Final
          </button>
        </div>
      </section>

      {/* Footer */}
      <footer className="bg-slate-950 text-slate-400 py-8 text-center text-sm">
        <p>&copy; 2026 Proiect de Candidatură Management. Creat ca un model demonstrativ de strategie executivă.</p>
        <p className="mt-2 text-slate-600">Nu este afiliat oficial cu BMW AG.</p>
      </footer>
    </div>
  );
}