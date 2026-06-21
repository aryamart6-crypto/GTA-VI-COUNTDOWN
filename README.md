# GTA-VI-COUNTDOWN
The HTML code for html gta vi countdown is:
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GTA VI — Countdown to Vice City</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Anton&family=Space+Grotesk:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg-0: #08030f;
    --bg-1: #1a0a2e;
    --pink: #ff2d7e;
    --orange: #ff7a3d;
    --yellow: #ffce3d;
    --teal: #2dd4bf;
    --cream: #fff5e6;
    --muted: rgba(255, 245, 230, 0.55);
    --glass: rgba(255, 255, 255, 0.04);
    --glass-strong: rgba(255, 255, 255, 0.07);
    --glass-border: rgba(255, 255, 255, 0.09);
  }
  * { box-sizing: border-box; margin: 0; padding: 0; }

  html, body {
    min-height: 100vh;
    font-family: 'Space Grotesk', system-ui, sans-serif;
    color: var(--cream);
    background: var(--bg-0);
    overflow-x: hidden;
    -webkit-font-smoothing: antialiased;
  }

  .liquid-bg {
    position: fixed; inset: 0; z-index: -3;
    background:
      radial-gradient(ellipse 80% 60% at 50% 110%, rgba(255, 122, 61, 0.55) 0%, transparent 60%),
      radial-gradient(ellipse 60% 50% at 20% 90%, rgba(255, 45, 126, 0.35) 0%, transparent 60%),
      radial-gradient(ellipse 50% 40% at 80% 95%, rgba(255, 206, 61, 0.25) 0%, transparent 60%),
      linear-gradient(180deg, #08030f 0%, #160826 30%, #2a0e3d 60%, #4d1a3d 100%);
  }

  .blob {
    position: fixed; border-radius: 50%; filter: blur(90px);
    opacity: 0.7; z-index: -2; pointer-events: none;
    mix-blend-mode: screen; will-change: transform;
  }
  .blob-1 { width: 540px; height: 540px; background: radial-gradient(circle, var(--pink) 0%, transparent 70%); top: -10%; left: -8%; animation: float1 22s ease-in-out infinite; }
  .blob-2 { width: 620px; height: 620px; background: radial-gradient(circle, var(--orange) 0%, transparent 70%); top: 40%; right: -12%; animation: float2 28s ease-in-out infinite; }
  .blob-3 { width: 460px; height: 460px; background: radial-gradient(circle, var(--yellow) 0%, transparent 70%); bottom: -5%; left: 25%; animation: float3 25s ease-in-out infinite; }
  .blob-4 { width: 380px; height: 380px; background: radial-gradient(circle, var(--teal) 0%, transparent 70%); top: 20%; left: 40%; opacity: 0.3; animation: float1 30s ease-in-out infinite reverse; }

  @keyframes float1 { 0%, 100% { transform: translate(0, 0) scale(1); } 33% { transform: translate(60px, -90px) scale(1.1); } 66% { transform: translate(-70px, 50px) scale(0.92); } }
  @keyframes float2 { 0%, 100% { transform: translate(0, 0) scale(1); } 50% { transform: translate(-90px, -70px) scale(1.15); } }
  @keyframes float3 { 0%, 100% { transform: translate(0, 0) scale(1); } 50% { transform: translate(80px, -60px) scale(1.05); } }

  .noise {
    position: fixed; inset: 0; z-index: -1; opacity: 0.06; pointer-events: none;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='3'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
  }

  .bg-vi {
    position: fixed; top: 50%; left: 50%; transform: translate(-50%, -50%);
    font-family: 'Anton', sans-serif; font-size: min(85vh, 90vw);
    color: rgba(255, 245, 230, 0.018); z-index: -1; pointer-events: none;
    letter-spacing: -0.08em; line-height: 0.85; user-select: none;
  }

  .particles { position: fixed; inset: 0; pointer-events: none; z-index: -1; overflow: hidden; }
  .particle { position: absolute; bottom: -10px; border-radius: 50%; animation: rise linear infinite; filter: blur(0.5px); }
  @keyframes rise { 0% { transform: translateY(0) translateX(0); opacity: 0; } 10% { opacity: 1; } 90% { opacity: 1; } 100% { transform: translateY(-110vh) translateX(60px); opacity: 0; } }

  .wave-layer { position: fixed; bottom: 0; left: 0; right: 0; height: 140px; z-index: -1; pointer-events: none; opacity: 0.5; }

  header { padding: 22px 40px; display: flex; justify-content: space-between; align-items: center; position: relative; z-index: 10; }
  .logo { display: flex; align-items: baseline; gap: 14px; }
  .logo-text { font-family: 'Anton', sans-serif; font-size: 18px; letter-spacing: 5px; color: var(--cream); text-transform: uppercase; }
  .logo-vi { font-family: 'Anton', sans-serif; font-size: 32px; background: linear-gradient(135deg, var(--pink) 0%, var(--orange) 50%, var(--yellow) 100%); -webkit-background-clip: text; background-clip: text; -webkit-text-fill-color: transparent; letter-spacing: 2px; line-height: 1; }
  .badge { display: inline-flex; align-items: center; gap: 9px; padding: 8px 16px; border-radius: 100px; background: var(--glass); border: 1px solid var(--glass-border); backdrop-filter: blur(20px); -webkit-backdrop-filter: blur(20px); font-size: 11px; letter-spacing: 2px; text-transform: uppercase; color: var(--muted); font-weight: 500; }
  .badge .dot { width: 7px; height: 7px; border-radius: 50%; background: var(--pink); box-shadow: 0 0 12px var(--pink), 0 0 24px var(--pink); animation: pulse 2s ease-in-out infinite; }
  @keyframes pulse { 0%, 100% { opacity: 1; transform: scale(1); } 50% { opacity: 0.4; transform: scale(1.4); } }

  .hero { min-height: calc(100vh - 80px); display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 40px 24px 80px; text-align: center; position: relative; z-index: 1; }
  .hero-tag { font-size: 12px; letter-spacing: 8px; text-transform: uppercase; color: var(--muted); margin-bottom: 24px; font-weight: 500; }
  .hero-tag::before, .hero-tag::after { content: ''; display: inline-block; width: 30px; height: 1px; background: linear-gradient(90deg, transparent, var(--muted)); vertical-align: middle; margin: 0 16px; }
  .hero-tag::after { background: linear-gradient(90deg, var(--muted), transparent); }

  .hero-title { font-family: 'Anton', sans-serif; font-size: clamp(44px, 8vw, 104px); line-height: 0.92; letter-spacing: -1px; margin: 0 0 20px; text-transform: uppercase; font-weight: 400; }
  .hero-title .accent { background: linear-gradient(135deg, var(--pink) 0%, var(--orange) 60%, var(--yellow) 100%); -webkit-background-clip: text; background-clip: text; -webkit-text-fill-color: transparent; display: inline-block; }
  .hero-subtitle { font-size: 16px; color: var(--muted); margin-bottom: 56px; max-width: 540px; line-height: 1.6; font-weight: 300; }

  .countdown { display: grid; grid-template-columns: repeat(4, 1fr); gap: 18px; max-width: 920px; width: 100%; margin-bottom: 40px; }
  .count-card { position: relative; padding: 36px 14px 26px; border-radius: 28px; background: var(--glass-strong); border: 1px solid var(--glass-border); backdrop-filter: blur(24px); -webkit-backdrop-filter: blur(24px); overflow: hidden; transition: transform 0.4s cubic-bezier(.2,.8,.2,1), box-shadow 0.4s ease, border-color 0.4s ease; }
  .count-card::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 1px; background: linear-gradient(90deg, transparent, var(--pink), var(--orange), var(--yellow), transparent); opacity: 0.6; }
  .count-card::after { content: ''; position: absolute; top: -50%; left: -100%; width: 60%; height: 200%; background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.06), transparent); transform: rotate(20deg); animation: sweep 6s ease-in-out infinite; pointer-events: none; }
  .count-card:nth-child(2)::after { animation-delay: -1.5s; }
  .count-card:nth-child(3)::after { animation-delay: -3s; }
  .count-card:nth-child(4)::after { animation-delay: -4.5s; }
  @keyframes sweep { 0%, 100% { left: -100%; } 50% { left: 150%; } }

  .count-card:hover { transform: translateY(-6px); border-color: rgba(255, 122, 61, 0.3); box-shadow: 0 20px 60px rgba(255, 45, 126, 0.18), 0 0 40px rgba(255, 122, 61, 0.1); }
  .count-card:hover .count-number { transform: scale(1.03); }

  .count-number { font-family: 'Anton', sans-serif; font-size: clamp(54px, 9vw, 92px); line-height: 1; background: linear-gradient(180deg, #ffffff 0%, #ffe8d4 60%, #ffc4a3 100%); -webkit-background-clip: text; background-clip: text; -webkit-text-fill-color: transparent; transition: transform 0.4s cubic-bezier(.2,.8,.2,1); font-variant-numeric: tabular-nums; position: relative; }
  .count-number.flip { animation: flip 0.55s cubic-bezier(.2,.8,.2,1); }
  @keyframes flip { 0% { transform: scale(1); filter: brightness(1); } 40% { transform: scale(1.12); filter: brightness(1.4); } 100% { transform: scale(1); filter: brightness(1); } }

  .count-label { font-size: 11px; letter-spacing: 4px; text-transform: uppercase; color: var(--muted); margin-top: 14px; font-weight: 500; }
  .release-date { font-size: 14px; color: var(--cream); letter-spacing: 3px; text-transform: uppercase; margin-bottom: 36px; opacity: 0.85; }
  .release-date strong { color: var(--orange); font-weight: 600; }

  .progress-section { max-width: 640px; width: 100%; }
  .progress-info { display: flex; justify-content: space-between; font-size: 11px; color: var(--muted); margin-bottom: 12px; letter-spacing: 2px; text-transform: uppercase; font-weight: 500; }
  .progress-bar { height: 6px; background: var(--glass); border-radius: 100px; overflow: hidden; border: 1px solid var(--glass-border); position: relative; }
  .progress-fill { height: 100%; background: linear-gradient(90deg, var(--pink) 0%, var(--orange) 50%, var(--yellow) 100%); border-radius: 100px; transition: width 1s ease; box-shadow: 0 0 20px rgba(255, 122, 61, 0.6); position: relative; overflow: hidden; }
  .progress-fill::after { content: ''; position: absolute; inset: 0; background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.4), transparent); animation: progressShine 2.5s ease-in-out infinite; }
  @keyframes progressShine { 0% { transform: translateX(-100%); } 100% { transform: translateX(200%); } }

  .info-section, .gallery-section { padding: 60px 40px 40px; max-width: 1200px; margin: 0 auto; position: relative; z-index: 1; }
  .section-title { font-family: 'Anton', sans-serif; font-size: clamp(32px, 5vw, 56px); text-align: center; margin-bottom: 12px; letter-spacing: 1px; text-transform: uppercase; font-weight: 400; }
  .section-title .accent { background: linear-gradient(135deg, var(--pink), var(--orange)); -webkit-background-clip: text; background-clip: text; -webkit-text-fill-color: transparent; }
  .section-subtitle { text-align: center; color: var(--muted); margin-bottom: 56px; font-size: 14px; letter-spacing: 2px; }

  /* === BIG Video Gallery === */
  .video-grid {
    display: flex;
    flex-direction: column;
    gap: 48px;
    max-width: 1000px;
    margin: 0 auto 40px;
  }

  .video-card {
    position: relative;
    border-radius: 28px;
    background: var(--glass-strong);
    border: 1px solid var(--glass-border);
    backdrop-filter: blur(24px);
    -webkit-backdrop-filter: blur(24px);
    overflow: hidden;
    transition: transform 0.4s cubic-bezier(.2,.8,.2,1), border-color 0.4s ease, box-shadow 0.4s ease;
  }
  .video-card::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 1px; background: linear-gradient(90deg, transparent, var(--pink), var(--orange), transparent); opacity: 0.4; z-index: 2; }
  .video-card:hover { transform: translateY(-4px); border-color: rgba(255, 122, 61, 0.35); box-shadow: 0 24px 80px rgba(255, 45, 126, 0.18), 0 0 60px rgba(255, 122, 61, 0.08); }

  .video-thumb {
    position: relative;
    padding-top: 56.25%;
    width: 100%;
    overflow: hidden;
    background: #000;
  }
  .video-thumb img {
    position: absolute; top: 0; left: 0; width: 100%; height: 100%;
    object-fit: cover;
    transition: transform 0.6s ease, opacity 0.4s ease;
    filter: saturate(1.1) contrast(1.05);
    z-index: 1;
  }
  .video-card:hover .video-thumb img { transform: scale(1.03); }

  .video-overlay {
    position: absolute; inset: 0;
    background: linear-gradient(180deg, rgba(8,3,15,0) 0%, rgba(8,3,15,0.3) 40%, rgba(8,3,15,0.85) 100%);
    display: flex; align-items: center; justify-content: center;
    transition: opacity 0.4s ease;
    z-index: 2;
    cursor: pointer;
  }

  .play-btn {
    width: 90px; height: 90px; border-radius: 50%;
    background: rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(10px); -webkit-backdrop-filter: blur(10px);
    border: 2px solid rgba(255, 255, 255, 0.6);
    display: flex; align-items: center; justify-content: center;
    transition: all 0.3s ease; position: relative;
    cursor: pointer;
  }
  .play-btn::before { content: ''; position: absolute; inset: -10px; border-radius: 50%; border: 2px solid var(--pink); opacity: 0; animation: pulseRing 2s infinite; }
  .video-card:hover .play-btn { background: var(--pink); border-color: var(--pink); transform: scale(1.12); box-shadow: 0 0 40px rgba(255, 45, 126, 0.6); }
  .play-btn svg { width: 34px; height: 34px; fill: white; margin-left: 5px; }

  @keyframes pulseRing { 0% { transform: scale(0.9); opacity: 0.7; } 100% { transform: scale(1.4); opacity: 0; } }

  /* The iframe sits inside video-thumb, hidden until play */
  .video-iframe {
    position: absolute; top: 0; left: 0; width: 100%; height: 100%;
    border: none; z-index: 5;
    display: none;
  }
  .video-iframe.active { display: block; }

  .stop-btn {
    position: absolute; top: 20px; right: 20px; width: 48px; height: 48px;
    border-radius: 50%; background: rgba(0,0,0,0.75);
    border: 1px solid rgba(255,255,255,0.3); color: white;
    cursor: pointer; display: none; align-items: center; justify-content: center;
    z-index: 10; transition: background 0.2s, transform 0.2s;
    backdrop-filter: blur(8px); -webkit-backdrop-filter: blur(8px);
  }
  .stop-btn.active { display: flex; }
  .stop-btn:hover { background: var(--pink); transform: rotate(90deg) scale(1.1); }
  .stop-btn svg { width: 22px; height: 22px; fill: currentColor; }

  .video-info { padding: 28px 36px 32px; }
  .video-info h3 { font-family: 'Anton', sans-serif; font-size: 28px; letter-spacing: 1px; margin-bottom: 10px; text-transform: uppercase; font-weight: 400; }
  .video-info p { color: var(--muted); font-size: 14px; line-height: 1.7; font-weight: 300; }
  .video-info .meta { margin-top: 16px; display: inline-flex; align-items: center; gap: 8px; font-size: 11px; letter-spacing: 2px; text-transform: uppercase; color: var(--orange); font-weight: 500; }

  .trailer-badge {
    position: absolute; top: 20px; left: 20px; z-index: 6;
    padding: 8px 18px; border-radius: 100px;
    background: rgba(0,0,0,0.6); backdrop-filter: blur(12px); -webkit-backdrop-filter: blur(12px);
    border: 1px solid rgba(255,255,255,0.15);
    font-family: 'Anton', sans-serif; font-size: 14px;
    letter-spacing: 3px; text-transform: uppercase; color: var(--cream);
    transition: opacity 0.3s ease;
  }
  .trailer-badge .badge-accent { color: var(--orange); }

  /* === Image Gallery (8 Image Bento Layout) === */
  .image-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-auto-rows: 220px;
    gap: 18px;
    max-width: 1100px;
    margin: 0 auto;
  }

  .image-item {
    position: relative;
    border-radius: 20px;
    overflow: hidden;
    cursor: pointer;
    border: 1px solid var(--glass-border);
    transition: transform 0.4s ease, border-color 0.4s ease;
  }

  /* Big Top Left Image */
  .image-item:nth-child(1) {
    grid-column: span 2;
    grid-row: span 2;
  }

  /* Tall Left Image (Middle) */
  .image-item:nth-child(4) {
    grid-row: span 2;
  }

  /* Wide Image (Middle Right) */
  .image-item:nth-child(7) {
    grid-column: span 2;
  }

  /* Panoramic Bottom Image */
  .image-item:nth-child(8) {
    grid-column: span 3;
  }

  .image-item img {
    width: 100%; height: 100%; object-fit: cover;
    transition: transform 0.6s cubic-bezier(.2,.8,.2,1), filter 0.4s ease;
    filter: saturate(1.1) contrast(1.05);
  }
  .image-item::after {
    content: ''; position: absolute; inset: 0;
    background: linear-gradient(180deg, transparent 50%, rgba(8,3,15,0.85) 100%);
    opacity: 0.8; transition: opacity 0.3s ease; pointer-events: none;
  }
  .image-item:hover {
    transform: translateY(-4px);
    border-color: var(--pink);
    z-index: 2;
  }
  .image-item:hover img { transform: scale(1.08); filter: saturate(1.4); }
  .image-item:hover::after { opacity: 0.4; }
  .image-tag {
    position: absolute; bottom: 16px; left: 16px;
    font-size: 12px; letter-spacing: 2px; text-transform: uppercase;
    color: var(--cream); font-weight: 600; z-index: 2;
    opacity: 0; transform: translateY(10px); transition: all 0.3s ease;
    text-shadow: 0 2px 10px rgba(0,0,0,0.5);
  }
  .image-item:hover .image-tag { opacity: 1; transform: translateY(0); }

  /* === Info grid === */
  .info-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 20px; }
  .info-card { position: relative; padding: 36px 32px; border-radius: 28px; background: var(--glass-strong); border: 1px solid var(--glass-border); backdrop-filter: blur(24px); -webkit-backdrop-filter: blur(24px); overflow: hidden; transition: transform 0.4s cubic-bezier(.2,.8,.2,1), border-color 0.4s ease; }
  .info-card::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 1px; background: linear-gradient(90deg, transparent, var(--pink), var(--orange), transparent); opacity: 0.4; }
  .info-card:hover { transform: translateY(-6px); border-color: rgba(255, 122, 61, 0.25); }
  .info-card .icon { width: 56px; height: 56px; border-radius: 18px; background: linear-gradient(135deg, var(--pink), var(--orange)); display: flex; align-items: center; justify-content: center; margin-bottom: 24px; box-shadow: 0 8px 24px rgba(255, 45, 126, 0.35); }
  .info-card .icon svg { width: 26px; height: 26px; fill: white; }
  .info-card h3 { font-family: 'Anton', sans-serif; font-size: 26px; letter-spacing: 1px; margin-bottom: 10px; text-transform: uppercase; font-weight: 400; }
  .info-card p { color: var(--muted); line-height: 1.7; font-size: 14px; font-weight: 300; margin-bottom: 14px; }
  .info-card p strong { color: var(--cream); font-weight: 500; }
  .info-card ul { list-style: none; padding: 0; margin-top: 10px; }
  .info-card ul li { color: var(--muted); font-size: 13px; padding: 6px 0; border-bottom: 1px solid rgba(255,255,255,0.05); display: flex; align-items: center; gap: 10px; }
  .info-card ul li:last-child { border-bottom: none; }
  .info-card ul li::before { content: '◆'; color: var(--orange); font-size: 8px; }
  .info-card .meta { margin-top: 18px; display: inline-flex; align-items: center; gap: 8px; font-size: 11px; letter-spacing: 2px; text-transform: uppercase; color: var(--orange); font-weight: 500; }

  .notify-section { padding: 40px 40px 100px; text-align: center; position: relative; z-index: 1; }
  .notify-card { max-width: 640px; margin: 0 auto; padding: 48px 40px; border-radius: 32px; background: var(--glass-strong); border: 1px solid var(--glass-border); backdrop-filter: blur(28px); -webkit-backdrop-filter: blur(28px); position: relative; overflow: hidden; }
  .notify-card::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 1px; background: linear-gradient(90deg, transparent, var(--pink), var(--yellow), var(--orange), transparent); opacity: 0.5; }
  .notify-card h2 { font-family: 'Anton', sans-serif; font-size: clamp(28px, 4vw, 40px); margin-bottom: 12px; letter-spacing: 1px; text-transform: uppercase; font-weight: 400; }
  .notify-card p { color: var(--muted); margin-bottom: 28px; font-size: 15px; font-weight: 300; }
  .notify-form { display: flex; gap: 12px; flex-wrap: wrap; max-width: 480px; margin: 0 auto; }
  .notify-input { flex: 1; min-width: 220px; padding: 16px 24px; border-radius: 100px; background: rgba(0, 0, 0, 0.35); border: 1px solid var(--glass-border); color: var(--cream); font-family: inherit; font-size: 14px; outline: none; transition: border-color 0.3s ease, box-shadow 0.3s ease; }
  .notify-input::placeholder { color: rgba(255, 245, 230, 0.35); }
  .notify-input:focus { border-color: var(--pink); box-shadow: 0 0 0 4px rgba(255, 45, 126, 0.12); }
  .notify-btn { padding: 16px 32px; border-radius: 100px; background: linear-gradient(135deg, var(--pink), var(--orange)); border: none; color: white; font-family: inherit; font-size: 13px; font-weight: 700; letter-spacing: 2px; text-transform: uppercase; cursor: pointer; transition: transform 0.3s ease, box-shadow 0.3s ease; position: relative; overflow: hidden; }
  .notify-btn::after { content: ''; position: absolute; inset: 0; background: linear-gradient(135deg, var(--orange), var(--yellow)); opacity: 0; transition: opacity 0.3s ease; }
  .notify-btn span { position: relative; z-index: 1; }
  .notify-btn:hover { transform: translateY(-2px); box-shadow: 0 12px 32px rgba(255, 45, 126, 0.45); }
  .notify-btn:hover::after { opacity: 1; }
  .notify-btn:active { transform: translateY(0); }

  footer { padding: 32px 40px; text-align: center; font-size: 11px; color: var(--muted); border-top: 1px solid var(--glass-border); letter-spacing: 1px; position: relative; z-index: 1; background: rgba(8, 3, 15, 0.4); backdrop-filter: blur(10px); -webkit-backdrop-filter: blur(10px); }

  .toast { position: fixed; bottom: 32px; left: 50%; transform: translateX(-50%) translateY(120px); padding: 14px 26px; background: rgba(20, 8, 30, 0.95); border: 1px solid var(--pink); border-radius: 100px; backdrop-filter: blur(20px); -webkit-backdrop-filter: blur(20px); color: var(--cream); font-size: 13px; letter-spacing: 1px; opacity: 0; transition: all 0.45s cubic-bezier(.2,.8,.2,1); z-index: 150; box-shadow: 0 12px 40px rgba(255, 45, 126, 0.35); display: flex; align-items: center; gap: 10px; pointer-events: none; }
  .toast.show { opacity: 1; transform: translateX(-50%) translateY(0); }
  .toast .toast-dot { width: 8px; height: 8px; border-radius: 50%; background: var(--pink); box-shadow: 0 0 10px var(--pink); }

  .released .hero-title { color: var(--yellow); }
  .released .countdown { display: none; }
  .released .release-date { font-size: 22px; }

  @media (max-width: 768px) {
    header { padding: 16px 20px; }
    .logo-text { font-size: 14px; letter-spacing: 3px; }
    .logo-vi { font-size: 24px; }
    .badge { padding: 6px 12px; font-size: 10px; }
    .hero { padding: 20px 16px 60px; }
    .countdown { grid-template-columns: repeat(2, 1fr); gap: 12px; }
    .count-card { padding: 26px 10px 20px; border-radius: 22px; }
    .info-section, .notify-section, .gallery-section { padding: 40px 16px; }
    .video-info { padding: 20px 20px 24px; }
    .video-info h3 { font-size: 22px; }
    .video-grid { gap: 32px; }
    .notify-card { padding: 32px 24px; }
    .notify-form { flex-direction: column; }
    .notify-btn { width: 100%; }
    
    /* Mobile Bento Layout */
    .image-grid {
      grid-template-columns: repeat(2, 1fr);
      grid-auto-rows: 140px;
      gap: 12px;
    }
    .image-item:nth-child(n) {
      grid-column: span 1;
      grid-row: span 1;
    }
    .image-item:nth-child(1) {
      grid-column: span 2; /* Hero takes full width */
      grid-row: span 2;
    }
    .image-item:nth-child(8) {
      grid-column: span 2; /* Panoramic takes full width */
    }

    .play-btn { width: 70px; height: 70px; }
    .play-btn svg { width: 28px; height: 28px; }
    .trailer-badge { top: 12px; left: 12px; padding: 6px 14px; font-size: 12px; }
    .stop-btn { top: 12px; right: 12px; width: 40px; height: 40px; }
    .stop-btn svg { width: 18px; height: 18px; }
  }

  @media (prefers-reduced-motion: reduce) {
    .blob, .particle, .count-card::after, .progress-fill::after { animation: none !important; }
    .count-number.flip { animation: none; }
  }
</style>
</head>
<body>
  <div class="liquid-bg"></div>
  <div class="blob blob-1"></div>
  <div class="blob blob-2"></div>
  <div class="blob blob-3"></div>
  <div class="blob blob-4"></div>
  <div class="bg-vi">VI</div>
  <div class="noise"></div>
  <div class="particles" id="particles"></div>

  <svg class="wave-layer" viewBox="0 0 1440 140" preserveAspectRatio="none">
    <path fill="rgba(255, 45, 126, 0.12)" d="M0,80 Q360,20 720,80 T1440,80 V140 H0 Z">
      <animate attributeName="d" values="M0,80 Q360,20 720,80 T1440,80 V140 H0 Z; M0,80 Q360,140 720,80 T1440,80 V140 H0 Z; M0,80 Q360,20 720,80 T1440,80 V140 H0 Z" dur="9s" repeatCount="indefinite"/>
    </path>
    <path fill="rgba(255, 122, 61, 0.10)" d="M0,100 Q480,50 960,100 T1440,100 V140 H0 Z">
      <animate attributeName="d" values="M0,100 Q480,50 960,100 T1440,100 V140 H0 Z; M0,100 Q480,150 960,100 T1440,100 V140 H0 Z; M0,100 Q480,50 960,100 T1440,100 V140 H0 Z" dur="12s" repeatCount="indefinite"/>
    </path>
  </svg>

  <header>
    <div class="logo">
      <span class="logo-text">Grand Theft Auto</span>
      <span class="logo-vi">VI</span>
    </div>
    <div class="badge">
      <span class="dot"></span>
      <span>Live Countdown</span>
    </div>
  </header>

  <main>
    <section class="hero" id="hero">
      <div class="hero-tag">Returning to Leonida</div>
      <h1 class="hero-title">Coming For <span class="accent">Everything</span></h1>
      <p class="hero-subtitle">Grand Theft Auto VI arrives on consoles and PC. Track every second until we ride back into Vice City.</p>

      <div class="countdown" id="countdown">
        <div class="count-card"><div class="count-number" id="days">000</div><div class="count-label">Days</div></div>
        <div class="count-card"><div class="count-number" id="hours">00</div><div class="count-label">Hours</div></div>
        <div class="count-card"><div class="count-number" id="minutes">00</div><div class="count-label">Minutes</div></div>
        <div class="count-card"><div class="count-number" id="seconds">00</div><div class="count-label">Seconds</div></div>
      </div>

      <p class="release-date">Arriving <strong>November 19, 2026</strong></p>

      <div class="progress-section">
        <div class="progress-info">
          <span>Trailer 1 — Dec 5, 2023</span>
          <span id="progress-percent">0%</span>
        </div>
        <div class="progress-bar">
          <div class="progress-fill" id="progress-fill" style="width: 0%"></div>
        </div>
      </div>
    </section>

    <!-- Video Gallery — iframes embedded directly -->
    <section class="gallery-section">
      <h2 class="section-title">Official <span class="accent">Trailers</span></h2>
      <p class="section-subtitle">Click to watch the trailers directly on this page</p>
      <div class="video-grid">

        <!-- Trailer 1 -->
        <div class="video-card" id="video-card-1">
          <div class="video-thumb">
            <img src="https://img.youtube.com/vi/QdBZY2fkU-0/maxresdefault.jpg" alt="GTA VI Trailer 1 Thumbnail">
            <div class="video-overlay" id="overlay-1">
              <div class="play-btn">
                <svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg>
              </div>
            </div>
            <div class="trailer-badge" id="badge-1"><span class="badge-accent">Trailer</span> 01</div>
            <button class="stop-btn" id="stop-1" aria-label="Stop video">
              <svg viewBox="0 0 24 24"><path d="M19 6.41L17.59 5 12 10.59 6.41 5 5 6.41 10.59 12 5 17.59 6.41 19 12 13.41 17.59 19 19 17.59 13.41 12z"/></svg>
            </button>
            <iframe
              id="iframe-1"
              class="video-iframe"
              data-src="https://www.youtube.com/embed/QdBZY2fkU-0?si=W_cuXKCXoqPCcAcG&autoplay=1&rel=0&modestbranding=1"
              title="YouTube video player"
              frameborder="0"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
              referrerpolicy="strict-origin-when-cross-origin"
              allowfullscreen
            ></iframe>
          </div>
          <div class="video-info">
            <h3>Trailer 1: Welcome to Leonida</h3>
            <p>The debut trailer released on December 5, 2023, breaking viewing records within hours. It introduced the sun-soaked streets of Vice City, the dual protagonists, and the chaotic, social-media-fueled atmosphere of the modern state of Leonida.</p>
            <div class="meta">Dec 5, 2023</div>
          </div>
        </div>

        <!-- Trailer 2 -->
        <div class="video-card" id="video-card-2">
          <div class="video-thumb">
            <img src="https://img.youtube.com/vi/VQRLujxTm3c/maxresdefault.jpg" alt="GTA VI Trailer 2 Thumbnail">
            <div class="video-overlay" id="overlay-2">
              <div class="play-btn">
                <svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg>
              </div>
            </div>
            <div class="trailer-badge" id="badge-2"><span class="badge-accent">Trailer</span> 02</div>
            <button class="stop-btn" id="stop-2" aria-label="Stop video">
              <svg viewBox="0 0 24 24"><path d="M19 6.41L17.59 5 12 10.59 6.41 5 5 6.41 10.59 12 5 17.59 6.41 19 12 13.41 17.59 19 19 17.59 13.41 12z"/></svg>
            </button>
            <iframe
              id="iframe-2"
              class="video-iframe"
              data-src="https://www.youtube.com/embed/VQRLujxTm3c?si=wWwiGxiJ9Qpq9S-i&autoplay=1&rel=0&modestbranding=1"
              title="YouTube video player"
              frameborder="0"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
              referrerpolicy="strict-origin-when-cross-origin"
              allowfullscreen
            ></iframe>
          </div>
          <div class="video-info">
            <h3>Trailer 2: Lucia & Jason</h3>
            <p>The highly anticipated second trailer dropped on May 6, 2025, offering a deeper look at the Bonnie-and-Clyde narrative. It showcased new environments like the swamps of Leonardida, expanded gameplay mechanics, and a deeper look into the relationship at the heart of the game.</p>
            <div class="meta">May 6, 2025</div>
          </div>
        </div>

      </div>
    </section>

    <!-- Image Gallery -->
    <section class="gallery-section">
      <h2 class="section-title">Vice City <span class="accent">Visuals</span></h2>
      <p class="section-subtitle">A glimpse into the sun-soaked, neon-lit world of Leonida</p>
      <div class="image-grid">
        <div class="image-item">
          <img src="https://drive.google.com/thumbnail?id=1oUDbghXg6NWqTEyUadNhKVdZDxwZsOsI&sz=w1000" alt="Vice City Beach" onerror="this.onerror=null;this.src='https://images.unsplash.com/photo-1503595855261-9418f48a7b14?q=80&w=1000&auto=format&fit=crop';">
          <div class="image-tag">Vice Beach</div>
        </div>
        <div class="image-item">
          <img src="https://drive.google.com/thumbnail?id=14Q0zvcn5tCE0rW8X0AL1RCZHY-ugLzXR&sz=w1000" alt="Miami Skyline" onerror="this.onerror=null;this.src='https://images.unsplash.com/photo-1476611338391-8f4f83bd0d8b?q=80&w=800&auto=format&fit=crop';">
          <div class="image-tag">Downtown Skyline</div>
        </div>
        <div class="image-item">
          <img src="https://drive.google.com/thumbnail?id=17R6kT1eB1_v8L1Nrvo2SNy998irKnQtr&sz=w1000" alt="Neon Palms" onerror="this.onerror=null;this.src='https://images.unsplash.com/photo-1535560431098-668d9ad36936?q=80&w=800&auto=format&fit=crop';">
          <div class="image-tag">Neon Nights</div>
        </div>
        <div class="image-item">
          <img src="https://drive.google.com/thumbnail?id=1MO3XotYH3n6XkSDTGUOQJB4DGiQrJHFq&sz=w1000" alt="Convertible Car" onerror="this.onerror=null;this.src='https://images.unsplash.com/photo-1503376780353-7e6692767b70?q=80&w=800&auto=format&fit=crop';">
          <div class="image-tag">Ocean Drive</div>
        </div>
        <div class="image-item">
          <img src="https://drive.google.com/thumbnail?id=1Z7GP4KeHxmejryTqMByR-G9VV63M0zR8&sz=w1000" alt="Night Beach" onerror="this.onerror=null;this.src='https://images.unsplash.com/photo-1518611018170-10ab2d8e1e14?q=80&w=800&auto=format&fit=crop';">
          <div class="image-tag">Midnight Shore</div>
        </div>
        <div class="image-item">
          <img src="https://drive.google.com/thumbnail?id=1_lWtDOZhO6BOToieuAkLnS9042Jawb0w&sz=w1000" alt="Synthwave Sunset" onerror="this.onerror=null;this.src='https://images.unsplash.com/photo-1486325212027-8081e485255e?q=80&w=800&auto=format&fit=crop';">
          <div class="image-tag">Synthwave Sunsets</div>
        </div>
        <div class="image-item">
          <img src="https://drive.google.com/thumbnail?id=1nq4q6rr6yLcEaAWvDaqVstsHdiKv4OQn&sz=w1000" alt="Vice City Concept" onerror="this.onerror=null;this.src='https://images.unsplash.com/photo-1571903143756-a3c2c5c5d3f1?q=80&w=1000&auto=format&fit=crop';">
          <div class="image-tag">Leonida Wildlife</div>
        </div>
        <div class="image-item">
          <img src="https://drive.google.com/thumbnail?id=14lwc76-G9jS6d527EZLz8hSxnWMzCwiO&sz=w1000" alt="Vice City Panorama" onerror="this.onerror=null;this.src='https://images.unsplash.com/photo-1535498730771-e735b998cd64?q=80&w=1600&auto=format&fit=crop';">
          <div class="image-tag">The Map</div>
        </div>
      </div>
    </section>

    <!-- Everything We Know -->
    <section class="info-section">
      <h2 class="section-title">Everything We <span class="accent">Know</span></h2>
      <p class="section-subtitle">A breakdown of all officially confirmed details about Grand Theft Auto VI</p>
      <div class="info-grid">
        <article class="info-card">
          <div class="icon">
            <svg viewBox="0 0 24 24"><path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5a2.5 2.5 0 010-5 2.5 2.5 0 010 5z"/></svg>
          </div>
          <h3>The Setting</h3>
          <p><strong>Leonida State:</strong> GTA VI takes place in a modern-day reimagining of Florida. It goes far beyond just Vice City, encompassing beaches, swamps, rural towns, and major highways.</p>
          <ul>
            <li>Vice City (Miami-inspired metropolis)</li>
            <li>Vice Beaches & Ocean Drive</li>
            <li>Port Gellhorn (Panama City vibe)</li>
            <li>Leonida Keys (Florida Keys)</li>
            <li>Mount Kalaga (National Park/Swamps)</li>
          </ul>
          <div class="meta">Open World</div>
        </article>
        <article class="info-card">
          <div class="icon">
            <svg viewBox="0 0 24 24"><path d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"/></svg>
          </div>
          <h3>The Protagonists</h3>
          <p><strong>Lucia & Jason:</strong> For the first time in the HD era, the game features a female lead. Their story is described as a modern-day, ill-fated romance—deeply inspired by Bonnie and Clyde.</p>
          <ul>
            <li>Lucia: Recently released from Leonida State Penitentiary</li>
            <li>Jason: Her partner, looking for a way out of the criminal grind</li>
            <li>Relationship built on trust, loyalty, and necessity</li>
            <li>Seamless character switching (improved from GTA V)</li>
          </ul>
          <div class="meta">Dual Leads</div>
        </article>
        <article class="info-card">
          <div class="icon">
            <svg viewBox="0 0 24 24"><path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm-5 14H7v-2h7v2zm3-4H7v-2h10v2zm0-4H7V7h10v2z"/></svg>
          </div>
          <h3>Gameplay Mechanics</h3>
          <p><strong>Next-Gen Interactivity:</strong> Rockstar is pushing immersion further than ever. NPCs react dynamically to the player's actions and the time of day.</p>
          <ul>
            <li>Usable social media (parody of TikTok/Insta)</li>
            <li>Carrying and stowing weapons in trunks</li>
            <li>Dynamic inventory system on bodies</li>
            <li>Improved physics and ragdoll system</li>
            <li>Underwater swimming and diving returns</li>
          </ul>
          <div class="meta">Immersion</div>
        </article>
        <article class="info-card">
          <div class="icon">
            <svg viewBox="0 0 24 24"><path d="M21 3H3c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h5v2h8v-2h5c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm0 14H3V5h18v12z"/></svg>
          </div>
          <h3>Platforms & Release</h3>
          <p><strong>Release Strategy:</strong> The game is officially targeting a Fall 2025 window initially, but has been tracked for November 19, 2026.</p>
          <ul>
            <li>PlayStation 5 (Console launch exclusive)</li>
            <li>Xbox Series X|S</li>
            <li>PC release at a later date</li>
            <li>GTA Online to continue post-launch</li>
          </ul>
          <div class="meta">Next-Gen Only</div>
        </article>
        <article class="info-card">
          <div class="icon">
            <svg viewBox="0 0 24 24"><path d="M20.5 11H19V7c0-1.1-.9-2-2-2h-4V3.5C13 2.12 11.88 1 10.5 1S8 2.12 8 3.5V5H4c-1.1 0-1.99.9-1.99 2v3.8H3.5c1.49 0 2.7 1.21 2.7 2.7s-1.21 2.7-2.7 2.7H2V20c0 1.1.9 2 2 2h3.8v-1.5c0-1.49 1.21-2.7 2.7-2.7s2.7 1.21 2.7 2.7V22H17c1.1 0 2-.9 2-2v-4h1.5c1.38 0 2.5-1.12 2.5-2.5S21.88 11 20.5 11z"/></svg>
          </div>
          <h3>Development History</h3>
          <p><strong>A Long Road:</strong> Development began shortly after GTA V (2013), but was heavily delayed due to Red Dead Redemption 2 and the massive 2022 leak.</p>
          <ul>
            <li>Officially announced via Rockstar Newswire in Nov 2023</li>
            <li>Trailer 1 forced out early due to a leak</li>
            <li>Powered by RAGE 9 (Rockstar Advanced Game Engine)</li>
            <li>Budget reportedly over $1 Billion</li>
          </ul>
          <div class="meta">Rockstar Games</div>
        </article>
        <article class="info-card">
          <div class="icon">
            <svg viewBox="0 0 24 24"><path d="M12 3v10.55c-.59-.34-1.27-.55-2-.55-2.21 0-4 1.79-4 4s1.79 4 4 4 4-1.79 4-4V7h4V3h-6z"/></svg>
          </div>
          <h3>Culture & Vibe</h3>
          <p><strong>Sun, Sin, and Social Media:</strong> The world feels alive, reflecting modern Florida culture—from wild beach parties to the bizarre "Florida Man" headlines.</p>
          <ul>
            <li>Social media plays a massive role in-story</li>
            <li>Internet, radio, and TV parody modern culture</li>
            <li>Influencer culture heavily mocked</li>
            <li>Vice City radio stations feature modern hits</li>
          </ul>
          <div class="meta">Modern Era</div>
        </article>
      </div>
    </section>

    <section class="notify-section">
      <div class="notify-card">
        <h2>Never Miss The Drop</h2>
        <p>Get a reminder the moment the clock hits zero and the gates of Vice City swing open.</p>
        <form class="notify-form" id="notify-form">
          <input type="email" class="notify-input" placeholder="your@email.com" required aria-label="Email address">
          <button type="submit" class="notify-btn"><span>Notify Me</span></button>
        </form>
      </div>
    </section>
  </main>

  <footer>
    <p>Fan-made countdown experience. Grand Theft Auto VI and all related marks are trademarks of Rockstar Games. Not affiliated with Rockstar.</p>
  </footer>

  <div class="toast" id="toast" role="status" aria-live="polite">
    <span class="toast-dot"></span>
    <span id="toast-text">Notification saved</span>
  </div>

  <script>
    // === Countdown Logic ===
    const RELEASE_DATE = new Date(2026, 10, 19, 0, 0, 0).getTime();
    const ANNOUNCE_DATE = new Date(2023, 11, 5, 10, 0, 0).getTime();

    const el = {
      days: document.getElementById('days'), hours: document.getElementById('hours'),
      minutes: document.getElementById('minutes'), seconds: document.getElementById('seconds'),
      progressFill: document.getElementById('progress-fill'),
      progressPercent: document.getElementById('progress-percent'),
      hero: document.getElementById('hero'), countdown: document.getElementById('countdown'),
      form: document.getElementById('notify-form'), toast: document.getElementById('toast'),
      toastText: document.getElementById('toast-text')
    };

    const prev = { days: '', hours: '', minutes: '', seconds: '' };

    function pad(n, len = 2) { return String(Math.max(0, n)).padStart(len, '0'); }

    function setValue(node, key, value, len = 2) {
      const formatted = pad(value, len);
      if (prev[key] === formatted) return;
      prev[key] = formatted;
      node.textContent = formatted;
      node.classList.remove('flip');
      void node.offsetWidth;
      node.classList.add('flip');
    }

    function updateCountdown() {
      const now = Date.now();
      const distance = RELEASE_DATE - now;
      if (distance <= 0) {
        el.hero.classList.add('released');
        el.days.textContent = '000'; el.hours.textContent = '00';
        el.minutes.textContent = '00'; el.seconds.textContent = '00';
        el.progressFill.style.width = '100%';
        el.progressPercent.textContent = '100% — Out Now';
        return;
      }
      const d = Math.floor(distance / 86400000);
      const h = Math.floor((distance % 86400000) / 3600000);
      const m = Math.floor((distance % 3600000) / 60000);
      const s = Math.floor((distance % 60000) / 1000);
      setValue(el.days, 'days', d, 3);
      setValue(el.hours, 'hours', h, 2);
      setValue(el.minutes, 'minutes', m, 2);
      setValue(el.seconds, 'seconds', s, 2);
      const total = RELEASE_DATE - ANNOUNCE_DATE;
      const elapsed = now - ANNOUNCE_DATE;
      const percent = Math.min(100, Math.max(0, (elapsed / total) * 100));
      el.progressFill.style.width = percent.toFixed(2) + '%';
      el.progressPercent.textContent = percent.toFixed(1) + '% elapsed';
    }

    updateCountdown();
    const initialDelay = 1000 - (Date.now() % 1000);
    setTimeout(() => { updateCountdown(); setInterval(updateCountdown, 1000); }, initialDelay);

    // === Video Player Logic — iframes are in the HTML, we just toggle src ===
    function playVideo(num) {
      const iframe = document.getElementById('iframe-' + num);
      const overlay = document.getElementById('overlay-' + num);
      const badge = document.getElementById('badge-' + num);
      const stopBtn = document.getElementById('stop-' + num);
      const card = document.getElementById('video-card-' + num);
      const img = card.querySelector('.video-thumb img');

      // Set the src from data-src to start loading + playing
      iframe.src = iframe.dataset.src;
      iframe.classList.add('active');

      // Hide overlay and thumbnail
      overlay.style.opacity = '0';
      overlay.style.pointerEvents = 'none';
      if (img) img.style.opacity = '0';
      if (badge) badge.style.opacity = '0';

      // Show stop button
      stopBtn.classList.add('active');
    }

    function stopVideo(num) {
      const iframe = document.getElementById('iframe-' + num);
      const overlay = document.getElementById('overlay-' + num);
      const badge = document.getElementById('badge-' + num);
      const stopBtn = document.getElementById('stop-' + num);
      const card = document.getElementById('video-card-' + num);
      const img = card.querySelector('.video-thumb img');

      // Clear src to stop the video completely
      iframe.src = '';
      iframe.classList.remove('active');

      // Restore overlay and thumbnail
      overlay.style.opacity = '1';
      overlay.style.pointerEvents = 'auto';
      if (img) img.style.opacity = '1';
      if (badge) badge.style.opacity = '1';

      // Hide stop button
      stopBtn.classList.remove('active');
    }

    // Attach click handlers
    document.getElementById('overlay-1').addEventListener('click', () => playVideo(1));
    document.getElementById('stop-1').addEventListener('click', (e) => { e.stopPropagation(); stopVideo(1); });
    document.getElementById('overlay-2').addEventListener('click', () => playVideo(2));
    document.getElementById('stop-2').addEventListener('click', (e) => { e.stopPropagation(); stopVideo(2); });

    // === Notify Form ===
    function showToast(message) {
      el.toastText.textContent = message;
      el.toast.classList.add('show');
      clearTimeout(showToast._t);
      showToast._t = setTimeout(() => el.toast.classList.remove('show'), 4000);
    }

    el.form.addEventListener('submit', (e) => {
      e.preventDefault();
      const input = el.form.querySelector('input');
      const email = input.value.trim();
      if (!email) return;
      try {
        const list = JSON.parse(localStorage.getItem('gta6_notify_list') || '[]');
        if (!list.includes(email)) {
          list.push(email);
          localStorage.setItem('gta6_notify_list', JSON.stringify(list));
          showToast("You're on the list — see you in Vice City.");
        } else {
          showToast("You're already on the list. Stay tuned.");
        }
      } catch (err) {
        showToast("You're on the list — see you in Vice City.");
      }
      el.form.reset();
    });

    // === Particles ===
    (function createParticles() {
      const container = document.getElementById('particles');
      const colors = ['#ff2d7e', '#ff7a3d', '#ffce3d'];
      const count = window.innerWidth < 768 ? 12 : 22;
      for (let i = 0; i < count; i++) {
        const p = document.createElement('span');
        p.className = 'particle';
        p.style.left = Math.random() * 100 + '%';
        const duration = 12 + Math.random() * 14;
        const delay = -Math.random() * duration;
        p.style.animationDuration = duration + 's';
        p.style.animationDelay = delay + 's';
        const size = 3 + Math.random() * 5;
        p.style.width = p.style.height = size + 'px';
        const color = colors[Math.floor(Math.random() * colors.length)];
        p.style.background = `radial-gradient(circle, ${color} 0%, transparent 70%)`;
        p.style.boxShadow = `0 0 ${size * 2}px ${color}`;
        container.appendChild(p);
      }
    })();

    // === Mouse Parallax ===
    let mouseX = 0, mouseY = 0, rafId = null;
    const blobs = [
      { el: document.querySelector('.blob-1'), factor: 0.04 },
      { el: document.querySelector('.blob-2'), factor: -0.05 },
      { el: document.querySelector('.blob-3'), factor: 0.03 },
      { el: document.querySelector('.blob-4'), factor: -0.02 }
    ];
    document.addEventListener('mousemove', (e) => {
      mouseX = (e.clientX / window.innerWidth - 0.5) * 2;
      mouseY = (e.clientY / window.innerHeight - 0.5) * 2;
      if (rafId) return;
      rafId = requestAnimationFrame(() => {
        blobs.forEach(b => { if (b && b.el) b.el.style.translate = `${mouseX * 30 * b.factor}px ${mouseY * 30 * b.factor}px`; });
        rafId = null;
      });
    });

    // === Welcome back ===
    try {
      const list = JSON.parse(localStorage.getItem('gta6_notify_list') || '[]');
      if (list.length > 0) setTimeout(() => showToast(`Welcome back. ${list.length} notification${list.length > 1 ? 's' : ''} queued.`), 800);
    } catch (e) {}
  </script>
</body>
</html>
