---
author: Pulsethetic
pubDatetime: 2025-11-01T10:00:00Z
title: "Proyecto: Synesthetic Sequencer"
description: "Un visualizador de audio y secuenciador algorítmico construido con React, WebGL (Three.js) y una API de Python (FastAPI) para el análisis de audio."
tags: ["Code", "React", "WebGL", "Python", "Proyecto"]
# Imagen de placeholder
ogImage: "https://placehold.co/1200x630/212737/00FFFF?text=Proyecto+Code"
---

## El Desafío Técnico

Este proyecto nació de mi interés en el Live Coding y la visualización de datos. El objetivo era crear una herramienta web que pudiera analizar un *stream* de audio en tiempo real y generar visuales estéticos (con la estética Pulsethetic) usando WebGL, mientras permitía al usuario manipular la secuencia.

## Stack de Tecnologías

* **Frontend:** React (Hooks) y TypeScript.
* **Gráficos:** WebGL (manejado con `three.js` y `react-three-fiber`).
* **Backend:** Una micro-API en Python (FastAPI) para manejar el análisis de audio (FFT) y enviar los datos al *frontend* vía WebSockets.

### Reto Principal: El Rendimiento

El mayor desafío fue mantener un *framerate* fluido (60fps) en el navegador mientras se procesaban los datos del WebSocket y se renderizaban los *shaders* de WebGL.

```typescript
// Ejemplo de código del Hook de React para el WebSocket
import { useEffect, useState } from 'react';
import io from 'socket.io-client';

const useAudioAnalysis = (url) => {
  const [data, setData] = useState(null);

  useEffect(() => {
    const socket = io(url);
    socket.on('fft-data', (analysisData) => {
      // Optimización: Solo actualizar el estado si los datos son significativos
      if (analysisData.peak > 0.5) {
        setData(analysisData);
      }
    });

    return () => socket.disconnect();
  }, [url]);

  return data;
};