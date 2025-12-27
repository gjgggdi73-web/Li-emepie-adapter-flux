# Li-emepie-adapter-flux


<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Адаптер Rezovskiy</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #0c0c0c 0%, #1a1a2e 50%, #16213e 100%);
            color: #f0f0f0;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }
        
        .container {
            max-width: 800px;
            width: 100%;
            background: rgba(20, 20, 30, 0.95);
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.7);
            border: 1px solid rgba(255, 0, 0, 0.3);
            position: relative;
            overflow: hidden;
        }
        
        .container::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(90deg, #ff0000, #ff8800, #ffff00, #00ff00, #0088ff, #8800ff);
            z-index: 1;
        }
        
        .header {
            text-align: center;
            margin-bottom: 30px;
            position: relative;
        }
        
        .title {
            font-size: 32px;
            font-weight: 900;
            margin-bottom: 10px;
            background: linear-gradient(90deg, #ff0000, #ff8800, #ffff00);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            text-transform: uppercase;
            letter-spacing: 2px;
            text-shadow: 0 0 10px rgba(255, 0, 0, 0.5);
        }
        
        .subtitle {
            font-size: 18px;
            color: #aaa;
            margin-bottom: 5px;
        }
        
        /* Стили для круглого фото */
        .photo-circle-container {
            display: flex;
            justify-content: center;
            margin: 25px 0;
            position: relative;
        }
        
        .photo-circle {
            width: 250px;
            height: 250px;
            border-radius: 50%;
            overflow: hidden;
            border: 6px solid #ff0000;
            box-shadow: 
                0 0 25px rgba(255, 0, 0, 0.8),
                0 0 50px rgba(255, 0, 0, 0.5);
            position: relative;
            animation: rotateCircle 30s linear infinite;
            transition: all 0.5s ease;
            background: white;
        }
        
        .photo-circle img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            filter: brightness(1.2) contrast(1.1); /* Делаем фото светлее */
        }
        
        @keyframes rotateCircle {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        .links {
            display: flex;
            flex-direction: column;
            gap: 18px;
            margin-top: 30px;
        }
        
        .link-item {
            display: flex;
            align-items: center;
            padding: 15px 20px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 12px;
            border-left: 4px solid #ff0000;
            transition: all 0.3s ease;
            text-decoration: none;
            color: #f0f0f0;
        }
        
        .link-item:hover {
            background: rgba(255, 255, 255, 0.1);
            transform: translateX(5px);
            border-left-color: #00ff00;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
        }
        
        .link-icon {
            font-size: 24px;
            margin-right: 15px;
            width: 40px;
            text-align: center;
        }
        
        .link-content {
            flex: 1;
        }
        
        .link-title {
            font-weight: 600;
            font-size: 18px;
            margin-bottom: 3px;
        }
        
        .link-url {
            font-size: 14px;
            color: #aaa;
            word-break: break-all;
        }
        
        .link-arrow {
            color: #888;
            font-size: 20px;
        }
        
        .footer {
            margin-top: 40px;
            text-align: center;
            color: #777;
            font-size: 14px;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .music-player {
            display: flex;
            align-items: center;
            justify-content: center;
            background: rgba(0, 0, 0, 0.3);
            padding: 15px;
            border-radius: 12px;
            margin-top: 30px;
            gap: 15px;
            flex-wrap: wrap;
            border: 1px solid rgba(255, 0, 0, 0.3);
        }
        
        .music-info {
            flex: 1;
            min-width: 200px;
        }
        
        .song-title {
            font-weight: 600;
            font-size: 18px;
            color: #ff4444;
        }
        
        .song-artist {
            font-size: 14px;
            color: #aaa;
        }
        
        .music-controls {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .music-btn {
            background: rgba(255, 0, 0, 0.3);
            border: none;
            color: white;
            width: 45px;
            height: 45px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            font-size: 18px;
            transition: all 0.3s ease;
        }
        
        .music-btn:hover {
            background: rgba(255, 0, 0, 0.7);
            transform: scale(1.1);
        }
        
        .volume-slider {
            width: 100px;
            -webkit-appearance: none;
            height: 8px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 4px;
            outline: none;
        }
        
        .volume-slider::-webkit-slider-thumb {
            -webkit-appearance: none;
            width: 20px;
            height: 20px;
            background: #ff0000;
            border-radius: 50%;
            cursor: pointer;
        }
        
        @media (max-width: 768px) {
            .container {
                padding: 20px;
            }
            
            .title {
                font-size: 26px;
            }
            
            .link-item {
                padding: 12px 15px;
            }
            
            .photo-circle {
                width: 200px;
                height: 200px;
            }
            
            .music-player {
                flex-direction: column;
                text-align: center;
            }
            
            .volume-slider {
                width: 80px;
            }
        }
        
        @media (max-width: 480px) {
            .container {
                padding: 15px;
            }
            
            .title {
                font-size: 22px;
            }
            
            .photo-circle {
                width: 180px;
                height: 180px;
            }
        }
        
        .pulse {
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        
        .now-playing {
            color: #ff0000;
            text-shadow: 0 0 10px rgba(255, 0, 0, 0.7);
            font-weight: bold;
        }
        
        .music-active {
            background: rgba(255, 0, 0, 0.7);
            box-shadow: 0 0 15px rgba(255, 0, 0, 0.7);
        }
        
        .audio-status {
            font-size: 12px;
            color: #ff6666;
            margin-top: 5px;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1 class="title">This is my original adapter</h1>
            <p class="subtitle">Don't see each other on fakes 🔫</p>
        </div>
        
        <!-- Круглое фото без текста -->
        <div class="photo-circle-container">
            <div class="photo-circle">
                <!-- Ваше фото аватарки -->
                <img src="https://pixsafe.online/proxy?albumId=EpV2U&fileName=photo2025-12-2523-40-31_OLFMo.jpg" alt="Rezovskiy Avatar">
            </div>
        </div>
        
        <div class="links">
            <a href="https://t.me/userrezovskiy" class="link-item pulse">
                <div class="link-icon">✈️</div>
                <div class="link-content">
                    <div class="link-title">DM - ᴩᴇɜᴏʙᴄᴋий</div>
                    <div class="link-url">https://t.me/userrezovskiy</div>
                </div>
                <div class="link-arrow">🔫</div>
            </a>
            
            <a href="https://t.me/project_rezovskiy" class="link-item">
                <div class="link-icon">💵</div>
                <div class="link-content">
                    <div class="link-title">канал - @chanell</div>
                    <div class="link-url">https://t.me/project_rezovskiy</div>
                </div>
                <div class="link-arrow">🔗</div>
            </a>
            
            <a href="https://t.me/price_rezovskiy" class="link-item">
                <div class="link-icon">💲</div>
                <div class="link-content">
                    <div class="link-title">цена - @price</div>
                    <div class="link-url">https://t.me/price_rezovskiy</div>
                </div>
                <div class="link-arrow">🔗</div>
            </a>
            
            <a href="https://t.me/rezovskiy_kents" class="link-item">
                <div class="link-icon">❓</div>
                <div class="link-content">
                    <div class="link-title">кенты - @kents</div>
                    <div class="link-url">https://t.me/rezovskiy_kents</div>
                </div>
                <div class="link-arrow">🔗</div>
            </a>
            
            <a href="https://t.me/apathy_reps" class="link-item">
                <div class="link-icon">💬</div>
                <div class="link-content">
                    <div class="link-title">отзывы - @reps</div>
                    <div class="link-url">https://t.me/apathy_reps | https://t.me/price_licimerie</div>
                </div>
                <div class="link-arrow">🔗</div>
            </a>
            
            <a href="https://t.me/userlicemerie_gifts" class="link-item">
                <div class="link-icon">🗄</div>
                <div class="link-content">
                    <div class="link-title">подарок от резовского - @gift</div>
                    <div class="link-url">https://t.me/userlicemerie_gifts</div>
                </div>
                <div class="link-arrow">🔗</div>
            </a>
            
            <a href="https://t.me/projectfluxx" class="link-item">
                <div class="link-icon">🤩</div>
                <div class="link-content">
                    <div class="link-title">проект & клан - @project</div>
                    <div class="link-url">https://t.me/projectfluxx</div>
                </div>
                <div class="link-arrow">🔗</div>
            </a>
            
            <a href="https://t.me/rezovskiyShop" class="link-item">
                <div class="link-icon">💲</div>
                <div class="link-content">
                    <div class="link-title">магазин - @shop</div>
                    <div class="link-url">https://t.me/rezovskiyShop</div>
                </div>
                <div class="link-arrow">🔗</div>
            </a>
        </div>
        
        <div class="music-player">
            <div class="music-info">
                <div class="song-title">Face - Красной помадой</div>
                <div class="song-artist"><span class="now-playing">▶️ Сейчас играет</span></div>
                <div class="audio-status" id="audioStatus">Музыка загружается...</div>
            </div>
            
            <div class="music-controls">
                <button id="playBtn" class="music-btn music-active">
                    <i class="fas fa-play"></i>
                </button>
                <button id="pauseBtn" class="music-btn">
                    <i class="fas fa-pause"></i>
                </button>
                <button id="stopBtn" class="music-btn">
                    <i class="fas fa-stop"></i>
                </button>
                <input type="range" id="volumeSlider" class="volume-slider" min="0" max="1" step="0.1" value="0.7">
            </div>
        </div>
        
        <div class="footer">
            <p>Owner Clan #Flux and #Silent</p>
            <p style="margin-top: 10px;">Адаптер Rezovskiy © 2023</p>
        </div>
    </div>
    
    <!-- Аудио элемент с автовоспроизведением -->
    <audio id="bgMusic" loop autoplay>
        <source src="https://eu.hitmo-top.com/get/music/20170914/Face_-_Krasnojj_pomadojj_48537338.mp3" type="audio/mpeg">
        Ваш браузер не поддерживает аудио элемент.
    </audio>
    
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const audio = document.getElementById('bgMusic');
            const playBtn = document.getElementById('playBtn');
            const pauseBtn = document.getElementById('pauseBtn');
            const stopBtn = document.getElementById('stopBtn');
            const volumeSlider = document.getElementById('volumeSlider');
            const audioStatus = document.getElementById('audioStatus');
            
            // Устанавливаем громкость
            audio.volume = volumeSlider.value;
            
            // Улучшенное автовоспроизведение
            const autoPlayAudio = () => {
                // Пытаемся запустить музыку сразу
                const playPromise = audio.play();
                
                if (playPromise !== undefined) {
                    playPromise.then(() => {
                        console.log("Музыка успешно запущена автоматически");
                        audioStatus.textContent = "Музыка играет";
                        playBtn.classList.add('music-active');
                    }).catch(error => {
                        console.log("Автовоспроизведение заблокировано, требуется взаимодействие пользователя");
                        audioStatus.textContent = "Кликните по странице, чтобы включить музыку";
                        playBtn.classList.remove('music-active');
                        
                        // Включаем музыку при первом клике по странице
                        const enableAudioOnInteraction = () => {
                            audio.play().then(() => {
                                console.log("Музыка запущена после взаимодействия");
                                audioStatus.textContent = "Музыка играет";
                                playBtn.classList.add('music-active');
                            }).catch(e => {
                                console.log("Не удалось запустить музыку после взаимодействия", e);
                                audioStatus.textContent = "Ошибка загрузки музыки";
                            });
                            
                            // Удаляем обработчики после первого взаимодействия
                            document.removeEventListener('click', enableAudioOnInteraction);
                            document.removeEventListener('touchstart', enableAudioOnInteraction);
                            document.removeEventListener('keydown', enableAudioOnInteraction);
                        };
                        
                        // Добавляем обработчики для различных типов взаимодействия
                        document.addEventListener('click', enableAudioOnInteraction);
                        document.addEventListener('touchstart', enableAudioOnInteraction);
                        document.addEventListener('keydown', enableAudioOnInteraction);
                    });
                }
            };
            
            // Запускаем автовоспроизведение после загрузки страницы
            setTimeout(autoPlayAudio, 1000);
            
            // Обработчики для кнопок управления музыкой
            playBtn.addEventListener('click', function() {
                audio.play().then(() => {
                    playBtn.classList.add('music-active');
                    pauseBtn.classList.remove('music-active');
                    audioStatus.textContent = "Музыка играет";
                });
            });
            
            pauseBtn.addEventListener('click', function() {
                audio.pause();
                pauseBtn.classList.add('music-active');
                playBtn.classList.remove('music-active');
                audioStatus.textContent = "Музыка на паузе";
            });
            
            stopBtn.addEventListener('click', function() {
                audio.pause();
                audio.currentTime = 0;
                playBtn.classList.remove('music-active');
                pauseBtn.classList.remove('music-active');
                audioStatus.textContent = "Музыка остановлена";
                
                // Эффект нажатия на кнопку stop
                stopBtn.classList.add('music-active');
                setTimeout(() => {
                    stopBtn.classList.remove('music-active');
                }, 300);
            });
            
            volumeSlider.addEventListener('input', function() {
                audio.volume = volumeSlider.value;
                audioStatus.textContent = `Громкость: ${Math.round(volumeSlider.value * 100)}%`;
                setTimeout(() => {
                    if (!audio.paused) {
                        audioStatus.textContent = "Музыка играет";
                    }
                }, 1500);
            });
            
            // Управление анимацией фото при наведении
            const photoCircle = document.querySelector('.photo-circle');
            photoCircle.addEventListener('mouseenter', function() {
                this.style.animationPlayState = 'paused';
                this.style.transform = 'scale(1.05)';
            });
            
            photoCircle.addEventListener('mouseleave', function() {
                this.style.animationPlayState = 'running';
                this.style.transform = 'scale(1)';
            });
            
            // Пульсация для первой ссылки
            const firstLink = document.querySelector('.link-item.pulse');
            setInterval(() => {
                firstLink.classList.toggle('pulse');
            }, 4000);
            
            // Обновляем статус аудио при изменении состояния
            audio.addEventListener('playing', () => {
                audioStatus.textContent = "Музыка играет";
            });
            
            audio.addEventListener('pause', () => {
                audioStatus.textContent = "Музыка на паузе";
            });
            
            audio.addEventListener('ended', () => {
                audioStatus.textContent = "Музыка закончилась";
            });
            
            audio.addEventListener('error', () => {
                audioStatus.textContent = "Ошибка загрузки музыки";
                audioStatus.style.color = '#ff0000';
            });
        });
    </script>
</body>
</html>
