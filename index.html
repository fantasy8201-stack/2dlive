import React, { useState, useEffect, useRef } from 'react';
import { Upload, Layers, Eye, Cpu, Sliders, Play, Maximize, AlertCircle, CheckCircle } from 'lucide-react';

// Mock Component to simulate WebGL/Canvas rendering
// In a real app, this would use Pixi.js or Live2D Cubism Web SDK
const Live2DCanvas = ({ imageSrc, isProcessed, params }) => {
  const canvasRef = useRef(null);
  
  useEffect(() => {
    const canvas = canvasRef.current;
    if (!canvas || !imageSrc) return;
    
    const ctx = canvas.getContext('2d');
    const img = new Image();
    img.src = imageSrc;
    
    let animationFrameId;
    
    const render = () => {
      // Clear canvas
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      
      // Basic settings
      const w = canvas.width;
      const h = canvas.height;
      const centerX = w / 2;
      const centerY = h / 2;
      
      if (!isProcessed) {
        // Just draw the static image if not processed
        ctx.drawImage(img, 0, 0, w, h);
      } else {
        // SIMULATION OF LIVE 2D MESH DEFORMATION
        // This is a simplified visual representation logic
        
        // 1. Breathing Effect (Global Scale Y)
        const time = Date.now() * 0.002;
        const breathScale = 1 + Math.sin(time) * 0.005;
        
        // 2. Head Rotation Simulation (Perspective Warp approximation)
        const headX = params.headX * 20; 
        const headY = params.headY * 10;
        
        ctx.save();
        ctx.translate(centerX + headX, centerY + headY);
        ctx.scale(breathScale, breathScale);
        
        // Draw Back Hair (Simulated Layer)
        ctx.globalAlpha = 1;
        ctx.drawImage(img, -w/2, -h/2, w, h); // Base
        
        // Draw Face/Eyes (Simulated Blinking)
        // In real Live2D, this involves mesh vertex manipulation
        // Here we simulate blinking by scaling the eye region vertically
        const blinkScale = params.eyeOpen; 
        
        // Simulating Eye Layers (Visual feedback only)
        // Left Eye
        ctx.fillStyle = 'rgba(255, 255, 255, 0.2)';
        // Logic: If processed, we pretend we have separated layers
        // This visualizer just shows the 'concept'
        
        ctx.restore();
        
        // Overlay technical visualization (Mesh)
        ctx.strokeStyle = 'rgba(0, 255, 255, 0.3)';
        ctx.lineWidth = 1;
        ctx.beginPath();
        // Draw a grid to represent the mesh
        for(let i=0; i<w; i+=50) {
            ctx.moveTo(i + headX, 0);
            ctx.lineTo(i + headX, h);
        }
        for(let j=0; j<h; j+=50) {
            ctx.moveTo(0, j + headY + (Math.sin(j/50 + time)*5)); // Waving mesh effect
            ctx.lineTo(w, j + headY + (Math.sin(j/50 + time)*5));
        }
        ctx.stroke();
      }
      
      animationFrameId = requestAnimationFrame(render);
    };
    
    img.onload = render;
    if(img.complete) render();
    
    return () => cancelAnimationFrame(animationFrameId);
  }, [imageSrc, isProcessed, params]);

  return (
    <canvas 
      ref={canvasRef} 
      width={600} 
      height={800} 
      className="w-full h-full object-contain bg-gray-900 rounded-lg shadow-inner"
    />
  );
};

const ArchitectureApp = () => {
  const [file, setFile] = useState(null);
  const [processingState, setProcessingState] = useState('idle'); // idle, analyzing, splitting, rigging, complete
  const [activeTab, setActiveTab] = useState('preview');
  const [logs, setLogs] = useState([]);
  
  // Simulation Parameters for Live 2D
  const [params, setParams] = useState({
    headX: 0,
    headY: 0,
    eyeOpen: 1.0,
    mouthForm: 0.0,
    breath: 0.5
  });

  const addLog = (msg) => {
    setLogs(prev => [...prev, { time: new Date().toLocaleTimeString(), msg }]);
  };

  const handleFileUpload = (e) => {
    const uploadedFile = e.target.files[0];
    if (uploadedFile) {
      const url = URL.createObjectURL(uploadedFile);
      setFile(url);
      addLog(`Image loaded: ${uploadedFile.name}`);
      setProcessingState('idle');
    }
  };

  const startProcessing = async () => {
    if (!file) return;
    
    setProcessingState('analyzing');
    addLog("Connecting to Gemini 1.5 Pro API...");
    
    // Simulation of the AI Pipeline delay
    setTimeout(() => {
      addLog("Gemini: Semantic Analysis Complete. Detected: Face, Eyes(2), Mouth, Hair.");
      setProcessingState('splitting');
      
      setTimeout(() => {
        addLog("CV Engine: Generating Segmentation Masks (SAM)...");
        addLog("Gemini: Inpainting occluded background areas...");
        setProcessingState('rigging');
        
        setTimeout(() => {
          addLog("Mesh Gen: Delaunay Triangulation applied.");
          addLog("Auto-Rigging: Weights assigned to parameters.");
          setProcessingState('complete');
          addLog("System: Live 2D Model Ready.");
        }, 1500);
      }, 1500);
    }, 1500);
  };

  return (
    <div className="flex flex-col h-screen bg-gray-950 text-gray-100 font-sans selection:bg-cyan-900">
      {/* Header */}
      <header className="flex items-center justify-between px-6 py-4 border-b border-gray-800 bg-gray-900/50 backdrop-blur">
        <div className="flex items-center space-x-3">
          <Cpu className="w-6 h-6 text-cyan-400" />
          <h1 className="text-xl font-bold tracking-tight text-white">
            AUTO-LIVE2D <span className="text-cyan-400 text-sm font-normal ml-2">ARCHITECT PRO</span>
          </h1>
        </div>
        <div className="text-xs text-gray-500 font-mono">
          v2.4.0-stable | GPU Acceleration: ON
        </div>
      </header>

      {/* Main Workspace */}
      <main className="flex flex-1 overflow-hidden">
        
        {/* Left Panel: Controls & Upload */}
        <aside className="w-80 border-r border-gray-800 flex flex-col bg-gray-900/30">
          <div className="p-6 border-b border-gray-800">
            <h2 className="text-sm font-semibold text-gray-400 mb-4 uppercase tracking-wider">Input Source</h2>
            <div className="border-2 border-dashed border-gray-700 rounded-xl p-8 flex flex-col items-center justify-center hover:border-cyan-500 transition-colors cursor-pointer relative bg-gray-900">
              <input type="file" onChange={handleFileUpload} className="absolute inset-0 opacity-0 cursor-pointer" />
              <Upload className="w-8 h-8 text-gray-500 mb-2" />
              <span className="text-xs text-gray-400">Drop Raster Image or Click</span>
            </div>
          </div>

          <div className="p-6 flex-1 overflow-y-auto">
            <h2 className="text-sm font-semibold text-gray-400 mb-4 uppercase tracking-wider">Processing Pipeline</h2>
            
            <div className="space-y-4">
              <StepIndicator 
                status={processingState === 'idle' ? 'pending' : processingState === 'analyzing' ? 'active' : 'done'} 
                title="Semantic Analysis" 
                desc="Gemini Vision API"
              />
              <StepIndicator 
                status={processingState === 'splitting' ? 'active' : ['rigging', 'complete'].includes(processingState) ? 'done' : 'pending'} 
                title="Layer Separation" 
                desc="Segmentation & Inpainting"
              />
              <StepIndicator 
                status={processingState === 'rigging' ? 'active' : processingState === 'complete' ? 'done' : 'pending'} 
                title="Mesh & Rigging" 
                desc="Delaunay Triangulation"
              />
            </div>

            <button 
              onClick={startProcessing}
              disabled={!file || processingState !== 'idle'}
              className={`w-full mt-8 py-3 rounded-lg flex items-center justify-center space-x-2 font-bold transition-all ${
                !file || processingState !== 'idle' 
                  ? 'bg-gray-800 text-gray-500 cursor-not-allowed' 
                  : 'bg-gradient-to-r from-cyan-600 to-blue-600 hover:from-cyan-500 hover:to-blue-500 text-white shadow-lg shadow-cyan-900/20'
              }`}
            >
              {processingState === 'idle' ? (
                <>
                  <Play className="w-4 h-4" />
                  <span>INITIATE PIPELINE</span>
                </>
              ) : (
                <>
                  <div className="animate-spin h-4 w-4 border-2 border-white border-t-transparent rounded-full"></div>
                  <span className="uppercase">{processingState}...</span>
                </>
              )}
            </button>
          </div>
        </aside>

        {/* Center Panel: Viewport */}
        <section className="flex-1 flex flex-col min-w-0 bg-gray-950 relative">
          <div className="flex items-center space-x-1 p-2 bg-gray-900 border-b border-gray-800">
            <TabButton active={activeTab === 'preview'} onClick={() => setActiveTab('preview')} icon={<Maximize className="w-4 h-4"/>} label="Live Preview" />
            <TabButton active={activeTab === 'mesh'} onClick={() => setActiveTab('mesh')} icon={<Layers className="w-4 h-4"/>} label="Mesh / Layers" />
          </div>

          <div className="flex-1 p-8 flex items-center justify-center relative overflow-hidden">
            {file ? (
              <div className="relative shadow-2xl shadow-black rounded-lg border border-gray-800 overflow-hidden">
                <Live2DCanvas imageSrc={file} isProcessed={processingState === 'complete'} params={params} />
                
                {processingState !== 'idle' && processingState !== 'complete' && (
                  <div className="absolute inset-0 bg-black/60 backdrop-blur-sm flex flex-col items-center justify-center z-10">
                    <div className="text-cyan-400 font-mono text-xl animate-pulse">
                      PROCESSING DATA...
                    </div>
                    <div className="text-xs text-gray-400 mt-2 font-mono">
                      Generating Mesh Vertices
                    </div>
                  </div>
                )}
              </div>
            ) : (
              <div className="text-gray-600 flex flex-col items-center">
                <div className="w-16 h-16 border-2 border-gray-800 rounded-full flex items-center justify-center mb-4">
                  <Eye className="w-8 h-8 opacity-20" />
                </div>
                <p>No Visual Data Loaded</p>
              </div>
            )}
          </div>

          {/* Console Log */}
          <div className="h-32 bg-gray-900 border-t border-gray-800 p-2 font-mono text-xs overflow-y-auto">
            {logs.map((log, idx) => (
              <div key={idx} className="mb-1">
                <span className="text-gray-500">[{log.time}]</span> <span className="text-cyan-300">&gt;&gt;</span> {log.msg}
              </div>
            ))}
            <div className="text-cyan-500 animate-pulse">_</div>
          </div>
        </section>

        {/* Right Panel: Parameter Controls */}
        <aside className="w-72 border-l border-gray-800 bg-gray-900/30 flex flex-col">
          <div className="p-4 border-b border-gray-800 bg-gray-900">
            <h2 className="text-xs font-bold text-gray-300 uppercase flex items-center">
              <Sliders className="w-3 h-3 mr-2" />
              Live Parameters
            </h2>
          </div>
          
          <div className="p-6 space-y-8 flex-1 overflow-y-auto opacity-100 transition-opacity duration-500" style={{ opacity: processingState === 'complete' ? 1 : 0.5, pointerEvents: processingState === 'complete' ? 'auto' : 'none' }}>
            
            <ControlGroup title="Head Orientation">
              <SliderControl 
                label="Angle X" 
                value={params.headX} 
                min={-1} max={1} 
                onChange={(v) => setParams({...params, headX: v})} 
              />
              <SliderControl 
                label="Angle Y" 
                value={params.headY} 
                min={-1} max={1} 
                onChange={(v) => setParams({...params, headY: v})} 
              />
            </ControlGroup>

            <ControlGroup title="Facial Features">
              <SliderControl 
                label="Eye Open" 
                value={params.eyeOpen} 
                min={0} max={1} 
                onChange={(v) => setParams({...params, eyeOpen: v})} 
              />
              <SliderControl 
                label="Mouth Form" 
                value={params.mouthForm} 
                min={0} max={1} 
                onChange={(v) => setParams({...params, mouthForm: v})} 
              />
            </ControlGroup>

            <ControlGroup title="Physics">
              <SliderControl 
                label="Breath Rate" 
                value={params.breath} 
                min={0} max={1} 
                onChange={(v) => setParams({...params, breath: v})} 
              />
            </ControlGroup>

          </div>
        </aside>
      </main>
    </div>
  );
};

// Sub-components for UI consistency

const StepIndicator = ({ status, title, desc }) => {
  const getIcon = () => {
    if (status === 'done') return <CheckCircle className="w-5 h-5 text-green-500" />;
    if (status === 'active') return <div className="w-5 h-5 border-2 border-cyan-400 border-t-transparent rounded-full animate-spin" />;
    return <div className="w-5 h-5 border-2 border-gray-700 rounded-full" />;
  };

  return (
    <div className={`flex items-start space-x-3 transition-colors ${status === 'pending' ? 'opacity-40' : 'opacity-100'}`}>
      <div className="pt-0.5">{getIcon()}</div>
      <div>
        <div className={`text-sm font-medium ${status === 'active' ? 'text-cyan-400' : 'text-gray-300'}`}>{title}</div>
        <div className="text-xs text-gray-500">{desc}</div>
      </div>
    </div>
  );
};

const TabButton = ({ active, onClick, icon, label }) => (
  <button 
    onClick={onClick}
    className={`flex items-center space-x-2 px-4 py-2 rounded text-xs font-medium transition-colors ${
      active ? 'bg-gray-800 text-white' : 'text-gray-500 hover:text-gray-300'
    }`}
  >
    {icon}
    <span>{label}</span>
  </button>
);

const ControlGroup = ({ title, children }) => (
  <div className="space-y-3">
    <h3 className="text-[10px] uppercase font-bold text-gray-500 tracking-wider">{title}</h3>
    {children}
  </div>
);

const SliderControl = ({ label, value, min, max, onChange }) => (
  <div>
    <div className="flex justify-between mb-1">
      <span className="text-xs text-gray-400">{label}</span>
      <span className="text-xs font-mono text-cyan-400">{value.toFixed(2)}</span>
    </div>
    <input 
      type="range" 
      min={min} 
      max={max} 
      step="0.01" 
      value={value}
      onChange={(e) => onChange(parseFloat(e.target.value))}
      className="w-full h-1 bg-gray-700 rounded-lg appearance-none cursor-pointer accent-cyan-500"
    />
  </div>
);

export default ArchitectureApp;
