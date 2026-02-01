<!DOCTYPE html>
<html lang="he" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>משמרת החצות - הסיוט של רובין</title>
    
    <!-- Tailwind CSS CDN -->
    <script src='https://cdn.tailwindcss.com'></script>
    <script>
        // Custom Tailwind Configuration for "Midnight Vigil" Theme
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        'midnight': '#000000',
                        'dark-gotham': '#1a1a1a',
                        'light-gotham': '#333333',
                        'accent-yellow': '#ffcc00',
                        'accent-red': '#cc0000',
                    },
                    fontFamily: {
                        sans: ['Arial', 'Helvetica', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    
    <!-- Minimal Custom CSS for Structure and Mobile Overrides -->
    <style>
        .comic-panel {
            /* Maintain 4:3 aspect ratio for dramatic comic framing */
            aspect-ratio: 4 / 3; 
        }
        .comic-panel img {
            object-fit: contain;
        }

        /* Responsive override: Move buttons to the bottom of the viewer on small screens */
        @media (max-width: 768px) {
            .nav-btn {
                top: auto !important;
                bottom: 5px;
                transform: none !important;
                padding: 5px 8px;
                font-size: 1.8em;
            }
            .nav-btn.prev-btn {
                right: 5px; /* Right side in RTL */
            }
            .nav-btn.next-btn {
                left: 5px; /* Left side in RTL */
            }
        }
    </style>
</head>

<body class="bg-midnight text-white min-h-screen flex flex-col font-sans">
    <header class="bg-dark-gotham p-4 border-b-2 border-accent-red flex justify-between items-center flex-wrap">
        
        <div class="logo flex items-center mb-2 md:mb-0">
            <span class="text-3xl text-accent-yellow ms-3">🦇</span>
            <h1 class="text-2xl font-bold text-accent-yellow tracking-wider">משמרת החצות</h1>
        </div>
        
        <div class="story-info text-left text-sm opacity-70">
            <h2 class="text-xl mb-0.5 text-white">הסיוט של רובין: פרק 1</h2>
            <p><strong class="font-normal">כתיבה:</strong> ג'ק ריידר | <strong class="font-normal">איור:</strong> הארלי קווין</p>
        </div>
    </header>

    <main class="comic-container flex-grow flex flex-col items-center p-5 max-w-6xl mx-auto w-full">
        <!-- מציג הקומיקס המרכזי -->
        <div class="viewer-wrapper relative w-full max-w-4xl mb-5">
            
            <!-- Previous Button (Right side in RTL) -->
            <button id="prev-btn" class="nav-btn prev-btn absolute top-1/2 -translate-y-1/2 
                                        bg-black/60 text-accent-yellow border-2 border-accent-yellow cursor-pointer 
                                        text-3xl p-3 z-10 transition duration-200 rounded-lg right-2 lg:right-4
                                        enabled:hover:bg-accent-yellow enabled:hover:text-black enabled:hover:border-black 
                                        disabled:opacity-30 disabled:cursor-default disabled:bg-light-gotham disabled:text-gray-500 disabled:border-gray-500" 
                    aria-label="שקופית קודמת">
                <span class="arrow">←</span>
            </button>
            
            <div id="comic-viewer" class="comic-panel border-4 border-dark-gotham bg-black overflow-hidden w-full flex justify-center items-center">
                <img id="current-slide-img" src="images/panel-1.jpg" alt="שקופית קומיקס: באטמן בעיר גות'האם" class="w-full h-full object-contain block" />
            </div>
            
            <!-- Next Button (Left side in RTL) -->
            <button id="next-btn" class="nav-btn next-btn absolute top-1/2 -translate-y-1/2 
                                        bg-black/60 text-accent-yellow border-2 border-accent-yellow cursor-pointer 
                                        text-3xl p-3 z-10 transition duration-200 rounded-lg left-2 lg:left-4
                                        enabled:hover:bg-accent-yellow enabled:hover:text-black enabled:hover:border-black 
                                        disabled:opacity-30 disabled:cursor-default disabled:bg-light-gotham disabled:text-gray-500 disabled:border-gray-500" 
                    aria-label="שקופית הבאה">
                <span class="arrow">→</span>
            </button>
        </div>

        <!-- מד התקדמות וניווט תחתון -->
        <div class="progress-area w-full max-w-4xl text-center pt-2">
            <div id="progress-text" class="text-lg mb-2 text-accent-yellow">שקופית 1 מתוך 10</div>
            <div id="progress-dots" class="flex justify-center gap-2">
                <!-- הנקודות ייווצרו באמצעות JS -->
            </div>
        </div>
    </main>

    <script src="script.js"></script>
</body>
</html>



document.addEventListener('DOMContentLoaded', () => {
    const totalSlides = 10;
    let currentSlide = 1;

    // DOM Elements
    const imgElement = document.getElementById('current-slide-img');
    const nextBtn = document.getElementById('next-btn');
    const prevBtn = document.getElementById('prev-btn');
    const progressText = document.getElementById('progress-text');
    const progressDotsContainer = document.getElementById('progress-dots');

    // --- Utility Functions ---

    /**
     * עדכון מציג התמונה, הכפתורים ומד ההתקדמות.
     */
    function updateViewer() {
        // 1. עדכון תמונה (נניח שקיימים קבצים בשם panel-1.jpg עד panel-10.jpg)
        imgElement.src = `images/panel-${currentSlide}.jpg`;
        imgElement.alt = `שקופית קומיקס מספר ${currentSlide}`;

        // 2. עדכון טקסט התקדמות
        progressText.textContent = `שקופית ${currentSlide} מתוך ${totalSlides}`;

        // 3. ניהול כפתורי ניווט
        prevBtn.disabled = currentSlide === 1;
        nextBtn.disabled = currentSlide === totalSlides;

        // 4. עדכון נקודות ההתקדמות (באמצעות Tailwind classes)
        const dots = progressDotsContainer.querySelectorAll('.dot');
        dots.forEach((dot, index) => {
            const isActive = index + 1 === currentSlide;
            
            // Toggle color and scale based on active state
            dot.classList.toggle('bg-accent-yellow', isActive);
            dot.classList.toggle('bg-light-gotham', !isActive);
            dot.classList.toggle('scale-125', isActive);
        });
    }

    /**
     * יצירת נקודות מד ההתקדמות באופן דינמי
     */
    function initializeProgressDots() {
        for (let i = 1; i <= totalSlides; i++) {
            const dot = document.createElement('div');
            
            // Applying Tailwind utility classes for size, shape, and default color
            dot.classList.add('dot', 'w-3', 'h-3', 'bg-light-gotham', 'rounded-full', 'transition', 'duration-300', 'cursor-pointer');
            
            dot.dataset.slide = i;
            dot.setAttribute('role', 'button');
            dot.setAttribute('tabindex', '0');
            dot.setAttribute('aria-label', `עבור לשקופית ${i}`);
            
            // ניווט מהיר בלחיצה על הנקודה
            dot.addEventListener('click', () => {
                currentSlide = i;
                updateViewer();
            });

            progressDotsContainer.appendChild(dot);
        }
    }
    
    // --- Event Handlers ---

    function handleNext() {
        if (currentSlide < totalSlides) {
            currentSlide++;
            updateViewer();
        }
    }

    function handlePrevious() {
        if (currentSlide > 1) {
            currentSlide--;
            updateViewer();
        }
    }

    // ניווט באמצעות כפתורים
    nextBtn.addEventListener('click', handleNext);
    prevBtn.addEventListener('click', handlePrevious);

    // ניווט נגיש באמצעות מקלדת (Accessibility)
    document.addEventListener('keydown', (event) => {
        // ArrowRight (חץ ימין) ב-RTL = הבא
        if (event.key === 'ArrowRight') {
            handleNext();
        } 
        // ArrowLeft (חץ שמאל) ב-RTL = הקודם
        else if (event.key === 'ArrowLeft') {
            handlePrevious();
        }
    });

    // --- Initialization ---
    initializeProgressDots();
    // הצגת השקופית הראשונה ועדכון המצב
    updateViewer(); 
});
