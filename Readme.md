import React, { useState, useEffect } from 'react';
import { 
  Terminal, 
  Code2, 
  Layers, 
  Globe, 
  Cpu, 
  Github, 
  ExternalLink, 
  Smartphone, 
  Database,
  Coffee,
  Cloud,
  Zap
} from 'lucide-react';

const App = () => {
  const [activeTab, setActiveTab] = useState('profile');
  const [typingText, setTypingText] = useState('');
  const fullText = "> bimaadam --status active --mode building_future";

  useEffect(() => {
    let i = 0;
    const interval = setInterval(() => {
      setTypingText(fullText.slice(0, i));
      i++;
      if (i > fullText.length) clearInterval(interval);
    }, 50);
    return () => clearInterval(interval);
  }, []);

  const stacks = {
    languages: [
      { name: 'Java', color: 'bg-orange-600', icon: '☕' },
      { name: 'TypeScript', color: 'bg-blue-600', icon: 'TS' },
      { name: 'PHP', color: 'bg-indigo-600', icon: '🐘' },
      { name: 'Go', color: 'bg-cyan-500', icon: 'GO' },
      { name: 'Rust', color: 'bg-orange-700', icon: '🦀' },
    ],
    frameworks: [
      { name: 'Spring Boot', color: 'bg-green-600', type: 'Backend' },
      { name: 'Next.js', color: 'bg-black', type: 'Fullstack' },
      { name: 'NestJS', color: 'bg-red-600', type: 'Backend' },
      { name: 'Laravel', color: 'bg-rose-600', type: 'Backend' },
      { name: 'React', color: 'bg-sky-500', type: 'Frontend' },
    ],
    infra: [
      { name: 'PostgreSQL', icon: <Database size={16} /> },
      { name: 'Docker', icon: <Cloud size={16} /> },
      { name: 'GitHub Actions', icon: <Zap size={16} /> },
      { name: 'Linux', icon: <Cpu size={16} /> },
    ]
  };

  return (
    <div className="min-h-screen bg-[#0d1117] text-slate-300 font-mono p-4 md:p-8">
      <div className="max-w-4xl mx-auto space-y-6">
        
        {/* Header Section */}
        <header className="bg-[#161b22] border border-[#30363d] rounded-xl p-6 shadow-2xl relative overflow-hidden">
          <div className="absolute top-0 right-0 p-4 opacity-10">
            <Terminal size={120} />
          </div>
          
          <div className="flex flex-col md:flex-row justify-between items-start md:items-center gap-4">
            <div>
              <h1 className="text-3xl font-bold text-white flex items-center gap-3">
                BIMA ADAM <span className="text-xs bg-green-500/20 text-green-400 px-2 py-1 rounded border border-green-500/30 font-normal">OPEN TO REMOTE</span>
              </h1>
              <p className="text-blue-400 mt-1 flex items-center gap-2">
                <Code2 size={18} /> Fullstack Engineer & Founder @ IgnitronDev
              </p>
            </div>
            <div className="flex gap-3">
              <a href="https://github.com/bimaadam" className="p-2 bg-[#21262d] hover:bg-[#30363d] rounded-lg transition-colors border border-[#30363d]">
                <Github size={20} />
              </a>
              <button className="flex items-center gap-2 bg-blue-600 hover:bg-blue-500 text-white px-4 py-2 rounded-lg text-sm font-bold transition-all shadow-lg shadow-blue-900/20">
                Contact Me <ExternalLink size={14} />
              </button>
            </div>
          </div>

          <div className="mt-6 bg-[#0d1117] rounded-lg p-4 border border-[#30363d] font-mono text-sm">
            <div className="flex gap-2 mb-2">
              <div className="w-3 h-3 rounded-full bg-red-500/50"></div>
              <div className="w-3 h-3 rounded-full bg-yellow-500/50"></div>
              <div className="w-3 h-3 rounded-full bg-green-500/50"></div>
            </div>
            <span className="text-green-400">{typingText}</span>
            <span className="animate-pulse">_</span>
          </div>
        </header>

        {/* Main Grid */}
        <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
          
          {/* Sidebar / Metadata */}
          <div className="space-y-6">
            <section className="bg-[#161b22] border border-[#30363d] rounded-xl p-5">
              <h3 className="text-white text-sm font-bold mb-4 flex items-center gap-2 uppercase tracking-widest">
                <Layers size={16} className="text-blue-400" /> profile.yaml
              </h3>
              <div className="space-y-3 text-xs leading-relaxed">
                <div><span className="text-pink-400">location:</span> <span className="text-slate-400">Boyolali, Indonesia</span></div>
                <div><span className="text-pink-400">focus:</span> <span className="text-slate-400">EMR & FinTech Systems</span></div>
                <div><span className="text-pink-400">experience:</span> <span className="text-slate-400">5+ Years Fullstack</span></div>
                <div><span className="text-pink-400">current_os:</span> <span className="text-slate-400">Android 17 Beta (Pixel 6a)</span></div>
                <div className="pt-2">
                  <span className="text-pink-400">interests:</span>
                  <ul className="pl-4 mt-1 space-y-1">
                    <li className="text-slate-400">- System Architecture</li>
                    <li className="text-slate-400">- Scalable Infrastructure</li>
                  </ul>
                </div>
              </div>
            </section>

            <section className="bg-[#161b22] border border-[#30363d] rounded-xl p-5">
              <h3 className="text-white text-sm font-bold mb-4 flex items-center gap-2 uppercase tracking-widest">
                <Smartphone size={16} className="text-green-400" /> Active Hardware
              </h3>
              <div className="flex items-center gap-3 p-3 bg-[#0d1117] rounded-lg border border-[#30363d]">
                <div className="w-10 h-10 bg-slate-800 rounded flex items-center justify-center text-xl">📱</div>
                <div>
                  <div className="text-xs font-bold text-white">Google Pixel 6a</div>
                  <div className="text-[10px] text-slate-500">Android 17 Developer Preview</div>
                </div>
              </div>
            </section>
          </div>

          {/* Center / Stack Content */}
          <div className="md:col-span-2 space-y-6">
            <section className="bg-[#161b22] border border-[#30363d] rounded-xl p-6">
              <h3 className="text-white text-lg font-bold mb-6 flex items-center gap-2">
                <Cpu size={20} className="text-purple-400" /> stack.core
              </h3>
              
              <div className="space-y-8">
                {/* Languages */}
                <div>
                  <h4 className="text-xs font-bold text-slate-500 uppercase mb-3 flex items-center gap-2">
                    Languages <div className="h-px flex-1 bg-[#30363d]"></div>
                  </h4>
                  <div className="flex flex-wrap gap-2">
                    {stacks.languages.map(lang => (
                      <span key={lang.name} className={`px-3 py-1.5 rounded-md text-xs font-bold text-white ${lang.color} flex items-center gap-2 shadow-lg`}>
                        <span className="opacity-80 text-sm">{lang.icon}</span> {lang.name}
                      </span>
                    ))}
                  </div>
                </div>

                {/* Frameworks */}
                <div>
                  <h4 className="text-xs font-bold text-slate-500 uppercase mb-3 flex items-center gap-2">
                    Frameworks <div className="h-px flex-1 bg-[#30363d]"></div>
                  </h4>
                  <div className="grid grid-cols-2 gap-3">
                    {stacks.frameworks.map(fw => (
                      <div key={fw.name} className="flex items-center justify-between p-3 bg-[#0d1117] rounded-lg border border-[#30363d] hover:border-blue-500/50 transition-colors">
                        <span className="text-sm font-medium text-white">{fw.name}</span>
                        <span className="text-[10px] uppercase px-2 py-0.5 rounded bg-slate-800 text-slate-400">{fw.type}</span>
                      </div>
                    ))}
                  </div>
                </div>

                {/* Infra */}
                <div>
                  <h4 className="text-xs font-bold text-slate-500 uppercase mb-3 flex items-center gap-2">
                    Infrastructure <div className="h-px flex-1 bg-[#30363d]"></div>
                  </h4>
                  <div className="flex flex-wrap gap-4 text-sm">
                    {stacks.infra.map(item => (
                      <div key={item.name} className="flex items-center gap-2 text-slate-400">
                        <span className="text-blue-400">{item.icon}</span> {item.name}
                      </div>
                    ))}
                  </div>
                </div>
              </div>
            </section>

            {/* GitHub Stats Mockup */}
            <section className="grid grid-cols-2 md:grid-cols-4 gap-4">
              {[
                { label: 'Followers', val: '80+', color: 'text-blue-400' },
                { label: 'Stars', val: '120+', color: 'text-yellow-400' },
                { label: 'Repos', val: '45', color: 'text-purple-400' },
                { label: 'Uptime', val: '99.9%', color: 'text-green-400' }
              ].map(stat => (
                <div key={stat.label} className="bg-[#161b22] border border-[#30363d] rounded-xl p-4 text-center">
                  <div className={`text-xl font-bold ${stat.color}`}>{stat.val}</div>
                  <div className="text-[10px] text-slate-500 uppercase tracking-tighter">{stat.label}</div>
                </div>
              ))}
            </section>
          </div>
        </div>

        {/* Footer */}
        <footer className="text-center pt-8 pb-4 text-slate-500 text-xs">
          <p className="flex items-center justify-center gap-2">
            Built with <Coffee size={14} className="text-orange-500" /> by Bima Adam &copy; 2024
          </p>
        </footer>

      </div>
    </div>
  );
};

export default App;

