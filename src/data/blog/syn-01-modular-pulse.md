---
author: Pulsethetic
# CORRECCIÓN: 
# Cambiado a un formato de fecha ISO 8601 completo (Timestamp).
# AstroPaper lo requiere para validarlo como un objeto 'Date'.
pubDatetime: 2025-11-04T10:00:00Z
title: "SYN-01: Modular Pulse Sequence (TidalCycles)"
description: "Exploración de polirritmos complejos y síntesis FM. Esta sesión demuestra cómo una sintaxis de tres líneas puede construir un patrón evolutivo completo."
tags: ["Sound", "Live Coding", "TidalCycles", "Estética"]
---

### El Concepto
Esta sesión se enfoca en la exploración de polirritmos complejos y síntesis FM. El objetivo era demostrar cómo una sintaxis de tres líneas en TidalCycles puede construir un patrón evolutivo completo, combinando percusión, bajo y melodía.

### Video de la Sesión

<!-- Contenedor de video responsivo -->
<div class="relative pt-[56.25%] mb-8">
  <iframe
    class="absolute top-0 left-0 w-full h-full rounded-lg shadow-2xl shadow-accent/20"
    src="https://www.youtube.com/embed/YOUR_VIDEO_ID?modestbranding=1"
    title="YouTube video player"
    frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
    allowfullscreen
  ></iframe>
</div>

### Código (Live Snippet)

El núcleo de esta performance se basa en el siguiente *snippet* de TidalCycles:

<!-- Bloque de código con fondo oscuro y texto cian -->
<div class="bg-muted rounded-lg p-4 overflow-x-auto shadow-inner shadow-black/50">
  <pre class="text-cyan-300 text-sm">
    {`
    -- TidalCycles Code Block
    d1 $ s "bd*8 [hh*2 cp*4]" # speed 1.5
    d2 $ pF 0.5 $ sometimes (rev) $ struct "t(5,8)" $ sound "fm:3!4"
    d3 $ every 3 (slow 2) $ jux (rev) $ sound "arpy" # room 0.8
    `}
  </pre>
</div>
<p class="mt-4 text-sm text-foreground/75">
  *Este código genera un loop de percusión y añade un arpegio evolutivo. Ver repositorio para el archivo fuente completo.
</p>