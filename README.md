# 🎨 AI Art Studio - Galeria Interativa de Imagens IA

## 📒 Descrição
Projeto desenvolvido para o desafio #LabDIONattyOrNot da DIO. Uma aplicação interativa que explora e demonstra o poder das principais ferramentas de IA na geração de imagens.

## 🤖 Tecnologias Utilizadas
- **Claude AI** - Desenvolvimento e conceituação
- **React + Tailwind CSS** - Interface moderna
- **Lucide Icons** - Iconografia elegante

### IAs de Geração de Imagens Exploradas:
- Midjourney
- DALL-E 3
- Stable Diffusion
- Leonardo AI

## 🚀 Resultados
✅ Interface interativa e responsiva
✅ Showcase de 4 principais ferramentas
✅ Sistema de geração simulada
✅ Galeria visual atrativa
✅ Design futurista e moderno

Código:

import React, { useState } from 'react';
import { Sparkles, Wand2, Palette, Zap, Eye, Download, Info, ChevronRight, Star, ImageIcon } from 'lucide-react';

export default function AIArtStudio() {
  const [selectedStyle, setSelectedStyle] = useState(null);
  const [generating, setGenerating] = useState(false);
  const [showGallery, setShowGallery] = useState(false);

  const aiTools = [
    {
      id: 1,
      name: 'Midjourney',
      icon: Wand2,
      color: 'from-purple-500 to-pink-500',
      specialty: 'Arte Conceitual & Fantasia',
      description: 'Especialista em criar mundos fantásticos e conceitos visuais únicos',
      features: ['Hiper-realismo', 'Arte conceitual', 'Ilustrações detalhadas']
    },
    {
      id: 2,
      name: 'DALL-E 3',
      icon: Palette,
      color: 'from-green-500 to-emerald-500',
      specialty: 'Precisão & Realismo',
      description: 'Excelente entendimento de prompts e geração fotorrealística',
      features: ['Fotorrealismo', 'Compreensão de texto', 'Diversidade de estilos']
    },
    {
      id: 3,
      name: 'Stable Diffusion',
      icon: Zap,
      color: 'from-blue-500 to-cyan-500',
      specialty: 'Personalização Total',
      description: 'Open-source com controle total sobre o processo criativo',
      features: ['Código aberto', 'Modelos customizados', 'Controle avançado']
    },
    {
      id: 4,
      name: 'Leonardo AI',
      icon: ImageIcon,
      color: 'from-orange-500 to-red-500',
      specialty: 'Game Art & Design',
      description: 'Focado em assets para games e designs profissionais',
      features: ['Game assets', 'Consistência', 'Produção em escala']
    }
  ];

  const artStyles = [
    {
      id: 1,
      name: 'Cyberpunk Futurista',
      prompt: 'futuristic cyberpunk city at night, neon lights, rain, 4k',
      colors: ['#FF00FF', '#00FFFF', '#FF1493']
    },
    {
      id: 2,
      name: 'Fantasia Épica',
      prompt: 'epic fantasy landscape, floating islands, magical aurora, concept art',
      colors: ['#9370DB', '#FFD700', '#48D1CC']
    },
    {
      id: 3,
      name: 'Minimalista Moderno',
      prompt: 'minimalist modern architecture, clean lines, pastel colors',
      colors: ['#E6E6FA', '#F0E68C', '#B0E0E6']
    },
    {
      id: 4,
      name: 'Natureza Surrealista',
      prompt: 'surreal nature scene, dreamlike forest, ethereal lighting',
      colors: ['#228B22', '#DDA0DD', '#F0E68C']
    }
  ];

  const galleryImages = [
    { id: 1, style: 'Cyberpunk', tool: 'Midjourney', likes: 1247 },
    { id: 2, style: 'Fantasia', tool: 'DALL-E 3', likes: 892 },
    { id: 3, style: 'Minimalista', tool: 'Leonardo AI', likes: 2156 },
    { id: 4, style: 'Surrealista', tool: 'Stable Diffusion', likes: 1543 },
    { id: 5, style: 'Abstrato', tool: 'Midjourney', likes: 967 },
    { id: 6, style: 'Retro', tool: 'DALL-E 3', likes: 1823 }
  ];

  const handleGenerate = (style) => {
    setSelectedStyle(style);
    setGenerating(true);
    setTimeout(() => {
      setGenerating(false);
      setShowGallery(true);
    }, 2500);
  };

  return (
    <div className="min-h-screen bg-gradient-to-br from-indigo-950 via-purple-900 to-pink-900 text-white">
      {/* Hero Section */}
      <div className="relative overflow-hidden">
        <div className="absolute inset-0 bg-gradient-to-b from-transparent to-black/50" />
        <div className="relative max-w-7xl mx-auto px-6 py-20">
          <div className="text-center space-y-6">
            <div className="flex items-center justify-center gap-4 mb-6">
              <Sparkles className="w-16 h-16 text-yellow-400 animate-pulse" />
              <h1 className="text-6xl font-bold bg-gradient-to-r from-yellow-400 via-pink-400 to-purple-400 bg-clip-text text-transparent">
                AI Art Studio
              </h1>
            </div>
            <p className="text-2xl text-gray-200 max-w-3xl mx-auto">
              Explore o universo infinito da criação de imagens por Inteligência Artificial
            </p>
            <div className="flex items-center justify-center gap-6 text-sm text-gray-300">
              <span className="flex items-center gap-2">
                <Star className="w-5 h-5 text-yellow-400" />
                Qualidade Profissional
              </span>
              <span className="flex items-center gap-2">
                <Zap className="w-5 h-5 text-cyan-400" />
                Geração Instantânea
              </span>
              <span className="flex items-center gap-2">
                <Eye className="w-5 h-5 text-pink-400" />
                Infinitas Possibilidades
              </span>
            </div>
          </div>
        </div>
      </div>

      {/* AI Tools Section */}
      <div className="max-w-7xl mx-auto px-6 py-16">
        <div className="text-center mb-12">
          <h2 className="text-4xl font-bold mb-4">
            🤖 Principais Ferramentas de IA
          </h2>
          <p className="text-gray-300 text-lg">
            Conheça as IAs que estão revolucionando a criação visual
          </p>
        </div>

        <div className="grid md:grid-cols-2 lg:grid-cols-4 gap-6 mb-16">
          {aiTools.map((tool) => {
            const Icon = tool.icon;
            return (
              <div
                key={tool.id}
                className="group relative bg-white/5 backdrop-blur-lg rounded-2xl p-6 border border-white/10 hover:border-white/30 transition-all duration-300 hover:scale-105 hover:shadow-2xl"
              >
                <div className={`absolute inset-0 bg-gradient-to-br ${tool.color} opacity-0 group-hover:opacity-10 rounded-2xl transition-opacity duration-300`} />
                <div className="relative">
                  <div className={`w-16 h-16 bg-gradient-to-br ${tool.color} rounded-xl flex items-center justify-center mb-4`}>
                    <Icon className="w-8 h-8 text-white" />
                  </div>
                  <h3 className="text-xl font-bold mb-2">{tool.name}</h3>
                  <p className="text-sm text-gray-400 mb-4">{tool.specialty}</p>
                  <p className="text-sm text-gray-300 mb-4">{tool.description}</p>
                  <div className="space-y-2">
                    {tool.features.map((feature, idx) => (
                      <div key={idx} className="flex items-center gap-2 text-xs text-gray-400">
                        <ChevronRight className="w-4 h-4 text-cyan-400" />
                        <span>{feature}</span>
                      </div>
                    ))}
                  </div>
                </div>
              </div>
            );
          })}
        </div>

        {/* Art Styles Section */}
        <div className="text-center mb-12">
          <h2 className="text-4xl font-bold mb-4">
            🎨 Estilos Disponíveis
          </h2>
          <p className="text-gray-300 text-lg">
            Escolha um estilo e veja a mágica acontecer
          </p>
        </div>

        <div className="grid md:grid-cols-2 lg:grid-cols-4 gap-6 mb-16">
          {artStyles.map((style) => (
            <button
              key={style.id}
              onClick={() => handleGenerate(style)}
              className="group relative bg-gradient-to-br from-white/10 to-white/5 backdrop-blur-lg rounded-2xl p-6 border-2 border-white/20 hover:border-white/50 transition-all duration-300 hover:scale-105 hover:shadow-2xl"
            >
              <div className="flex gap-2 mb-4">
                {style.colors.map((color, idx) => (
                  <div
                    key={idx}
                    className="w-8 h-8 rounded-full"
                    style={{ backgroundColor: color }}
                  />
                ))}
              </div>
              <h3 className="text-xl font-bold mb-2">{style.name}</h3>
              <p className="text-sm text-gray-400 mb-4 italic">"{style.prompt}"</p>
              <div className="flex items-center justify-center gap-2 text-cyan-400 font-semibold">
                <Wand2 className="w-5 h-5" />
                <span>Gerar Imagem</span>
              </div>
            </button>
          ))}
        </div>

        {/* Generation Progress */}
        {generating && (
          <div className="fixed inset-0 bg-black/80 backdrop-blur-sm flex items-center justify-center z-50">
            <div className="bg-gradient-to-br from-purple-900/90 to-pink-900/90 rounded-3xl p-12 border border-white/20 max-w-md">
              <div className="text-center space-y-6">
                <div className="relative">
                  <Sparkles className="w-20 h-20 mx-auto text-yellow-400 animate-spin" />
                  <div className="absolute inset-0 bg-yellow-400/20 rounded-full blur-2xl animate-pulse" />
                </div>
                <h3 className="text-2xl font-bold">Criando sua obra de arte...</h3>
                <div className="space-y-2">
                  <div className="h-2 bg-white/20 rounded-full overflow-hidden">
                    <div className="h-full bg-gradient-to-r from-cyan-400 to-purple-400 rounded-full animate-progress" />
                  </div>
                  <p className="text-sm text-gray-300">Processando com {selectedStyle?.name}</p>
                </div>
              </div>
            </div>
          </div>
        )}

        {/* Gallery */}
        {showGallery && (
          <div className="mt-16">
            <div className="text-center mb-12">
              <h2 className="text-4xl font-bold mb-4">
                ✨ Galeria de Criações
              </h2>
              <p className="text-gray-300 text-lg">
                Imagens geradas por diferentes IAs
              </p>
            </div>

            <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
              {galleryImages.map((img) => (
                <div
                  key={img.id}
                  className="group relative aspect-square bg-gradient-to-br from-purple-500/20 to-pink-500/20 rounded-2xl overflow-hidden border border-white/10 hover:border-white/30 transition-all duration-300 hover:scale-105"
                >
                  <div className="absolute inset-0 bg-gradient-to-br from-purple-600 to-pink-600 opacity-50" />
                  <div className="absolute inset-0 flex items-center justify-center">
                    <ImageIcon className="w-24 h-24 text-white/30" />
                  </div>
                  <div className="absolute bottom-0 left-0 right-0 bg-gradient-to-t from-black/80 to-transparent p-6">
                    <div className="flex items-center justify-between">
                      <div>
                        <h4 className="font-bold text-lg">{img.style}</h4>
                        <p className="text-sm text-gray-300">{img.tool}</p>
                      </div>
                      <div className="flex items-center gap-2">
                        <Star className="w-5 h-5 text-yellow-400 fill-yellow-400" />
                        <span className="font-semibold">{img.likes}</span>
                      </div>
                    </div>
                  </div>
                </div>
              ))}
            </div>
          </div>
        )}

        {/* Info Section */}
        <div className="mt-16 bg-gradient-to-br from-cyan-900/30 to-purple-900/30 backdrop-blur-lg rounded-3xl p-12 border border-white/10">
          <div className="flex items-start gap-6">
            <Info className="w-12 h-12 text-cyan-400 flex-shrink-0" />
            <div className="space-y-4">
              <h3 className="text-3xl font-bold">💡 Sobre o Projeto</h3>
              <p className="text-gray-300 text-lg leading-relaxed">
                Este projeto foi desenvolvido para o desafio <span className="text-yellow-400 font-bold">#LabDIONattyOrNot</span> da 
                Digital Innovation One. O objetivo é explorar e demonstrar o poder das IAs Generativas na criação de imagens, 
                mostrando como essas ferramentas estão democratizando a arte digital e abrindo possibilidades infinitas 
                para criadores de todos os níveis.
              </p>
              <div className="flex flex-wrap gap-3 pt-4">
                <span className="px-4 py-2 bg-purple-500/20 rounded-full text-sm border border-purple-500/30">#IAGenerativa</span>
                <span className="px-4 py-2 bg-pink-500/20 rounded-full text-sm border border-pink-500/30">#ArteDigital</span>
                <span className="px-4 py-2 bg-cyan-500/20 rounded-full text-sm border border-cyan-500/30">#Midjourney</span>
                <span className="px-4 py-2 bg-yellow-500/20 rounded-full text-sm border border-yellow-500/30">#DALLE3</span>
                <span className="px-4 py-2 bg-green-500/20 rounded-full text-sm border border-green-500/30">#StableDiffusion</span>
              </div>
            </div>
          </div>
        </div>
      </div>

      {/* Footer */}
      <div className="border-t border-white/10 mt-16">
        <div className="max-w-7xl mx-auto px-6 py-8">
          <div className="text-center space-y-4">
            <p className="text-2xl font-bold bg-gradient-to-r from-yellow-400 to-pink-400 bg-clip-text text-transparent">
              Feito com 💜 e muita ✨ IA
            </p>
            <p className="text-gray-400">
              Desafio DIO • Natural ou Fake Natty? • 2025
            </p>
          </div>
        </div>
      </div>

      <style jsx>{`
        @keyframes progress {
          0% { width: 0%; }
          100% { width: 100%; }
        }
        .animate-progress {
          animation: progress 2.5s ease-in-out;
        }
      `}</style>
    </div>
  );
}
