# Design Specification / Спецификация дизайна

> EN: 8 styles. Each section: English first, Russian below; tables are shared.
> RU: 8 стилей. В каждом разделе сначала английская версия, ниже русская; таблицы общие.

## Styles / Стили

1. Hand-Drawn Doodle (手绘涂鸦风 / Рисованный дудл)
2. Parallax Sections (视差滚动 / Параллакс-секции)
3. Shader Gradient (着色器渐变 / Шейдерный градиент)
4. Apple Liquid Glass (Apple 流动玻璃 / Жидкое стекло)
5. Paper Craft (纸艺手作 / Бумажные ремёсла)
6. Bento Grid (便当盒布局 / Бенто-сетка)
7. Fullscreen Hero (全屏英雄区 / Полноэкранный герой)
8. Dopamine Design (多巴胺设计 / Дофаминовый дизайн)

---

## 1. Hand-Drawn Doodle (手绘涂鸦风)

### EN
Hand-drawn lines, doodle illustrations, irregular shapes, and handwritten fonts. Like designs casually sketched in a notebook — full of creativity and fun, conveying a warm and approachable handmade feel.

### RU
Рисованные линии, дудл-иллюстрации, неровные формы и «рукописные» шрифты. Как рисунки, небрежно набросанные в тетради — креативно и весело, с тёплым handmade-настроением.

| Token | Value / Значение |
| --- | --- |
| Primary / Основной | `#2c2c2c` |
| Secondary / Вторичный | `#fffef5` |
| Accent 1 / Акцент 1 | `#ff6b6b` |
| Accent 2 / Акцент 2 | `#4ecdc4` |
| Accent 3 / Акцент 3 | `#ffd93d` |
| Accent 4 / Акцент 4 | `#a98d16` |
| Border / Граница | `border-2 border-[#2c2c2c]` |
| Radius / Скругление | `rounded-sm` |
| Shadow (md) / Тень | `shadow-[3px_3px_0px_#4ecdc4]` |
| Shadow (hover) / Тень наведения | `hover:shadow-[6px_6px_0px_#4ecdc4]` |
| Heading font / Заголовки | `font-sans font-bold` |
| Body font / Основной текст | `font-sans` |
| Type scale / Масштаб текста | `text-4xl md:text-6xl lg:text-8xl` / `text-2xl md:text-4xl` / `text-sm md:text-base` |
| Spacing / Отступы | `py-12 md:py-20 lg:py-28` · `px-4 md:px-8 lg:px-12` · `p-5 md:p-8` |
| Gap / Промежутки | `gap-4 md:gap-6` |
| Transition / Переходы | `transition-all duration-200 ease-in-out` |
| Active / Активное состояние | `active:translate-x-[2px] active:translate-y-[2px] active:shadow-none` |

#### Never use in this style / Нельзя в этом стиле

- EN: `bg-gradient-to-r` — uses flat marker colors only, no gradients
- RU: `bg-gradient-to-r` — только плоские цвета маркеров, никаких градиентов
- EN: `bg-gradient-to-b`
- RU: `bg-gradient-to-b` (градиенты запрещены)
- EN: `shadow-md` — uses hard offset shadows (`shadow-[Npx_Npx_0px_color]`) to mimic marker strokes
- RU: `shadow-md` — только жёсткие офсетные тени (`shadow-[Npx_Npx_0px_color]`), имитирующие мазки маркера
- EN: `shadow-lg`
- RU: `shadow-lg` (запрещено)
- EN: `font-mono` — uses casual sans-serif fonts, never technical monospace
- RU: `font-mono` — только непринуждённый sans-serif, никаких технических monospace-шрифтов
- EN: `backdrop-blur` — opaque notebook paper, no blur or glass effects
- RU: `backdrop-blur` — непрозрачная тетрадная бумага, без блюра и стекла
- EN: `backdrop-blur-sm`
- RU: `backdrop-blur-sm` (запрещено)
- EN: `rounded-none` — uses rounded-sm for a slightly imprecise hand-drawn feel
- RU: `rounded-none` — используется rounded-sm для лёгкой «неточности» рисованного стиля

#### Do / Правила

- EN: Use dashed borders (`border-dashed`) to simulate hand-drawn lines
- RU: Используй пунктирные границы (`border-dashed`) для имитации рисованных линий
- EN: Use cream paper color `#fffef5` background
- RU: Используй кремовый «бумажный» фон `#fffef5`
- EN: Use ink black `#2c2c2c` as primary color
- RU: Используй чернильный чёрный `#2c2c2c` как основной цвет
- EN: Add subtle rotation to simulate hand-drawn irregularity
- RU: Добавляй лёгкий поворот (rotate) для имитации неровности рисунка
- EN: Use marker pen colors: red `#ff6b6b`, teal `#4ecdc4`, yellow `#ffd93d`
- RU: Используй цвета маркеров: красный `#ff6b6b`, бирюзовый `#4ecdc4`, жёлтый `#ffd93d`
- EN: Add notebook ruled-line backgrounds
- RU: Добавляй фоны с линованными тетрадными линиями
- EN: Use tape/pushpin/paperclip decorative elements
- RU: Используй декоративные элементы: скотч, канцелярские кнопки, скрепки

#### Don't / Запреты

- EN: Do not use precise geometric shapes and right angles (`rounded-none`)
- RU: Не используй точную геометрию и прямые углы (`rounded-none`)
- EN: Do not use gradient effects
- RU: Не используй градиенты
- EN: Do not use precise shadows (`shadow-md` etc.)
- RU: Не используй «точные» тени (`shadow-md` и т.п.)
- EN: Do not use monospace fonts
- RU: Не используй monospace-шрифты
- EN: Do not use solid borders (`border-solid`)
- RU: Не используй сплошные границы (`border-solid`)
- EN: Do not use large border radius (`rounded-lg` and above)
- RU: Не используй большое скругление (`rounded-lg` и выше)

Animations & interaction / Анимации и взаимодействия:
- EN: Stop-Motion Jitter: hover creates hand-drawn tremor through tiny rotations and displacements, avoiding smooth mechanical motion. Ink Filling: strengthen border thickness/color ("re-inking"). Offset Smudge: hard-edge offset shadows only; hover changes offset and marker color. Paper Press: active flattens shadow with slight scale (e.g. `scale-[0.98]`).
- RU: Стоп-моушен дрожание: при наведении элемент слегка «дрожит» микроповоротами и смещениями, без плавного механического движения. Заполнение чернилами: утолщение контура / усиление цвета («прорисовка ещё раз»). Офсетный «смаз»: только жёсткие офсетные тени; hover меняет сдвиг и цвет «второго мазка». Прижатие бумаги: активное состояние уменьшает scale (`scale-[0.98]`) и «придавливает» тень.

---

## 2. Parallax Sections (视差滚动)

### EN
An immersive layout creating depth parallax effects through fixed backgrounds and scrolling content, with each full-screen section having its own background layer. Ideal for brand stories, product showcases, and immersive experience pages.

### RU
Иммерсивный лейаут с эффектом глубины на параллаксе: фиксированный фон и скроллящийся контент, каждая полноэкранная секция со своим слоем фона. Идеально для бренд-стори, витрин продукта и иммерсивных страниц.

| Token | Value / Значение |
| --- | --- |
| Primary / Основной | `#1e3a5f` |
| Secondary / Вторичный | `#f8fafc` |
| Accent 1 / Акцент 1 | `#3b82f6` |
| Accent 2 / Акцент 2 | `#93c5fd` |
| Accent 3 / Акцент 3 | `#0ea5e9` |
| Accent 4 / Акцент 4 | `#c559f0` |
| Border / Граница | `border border-white/20` |
| Radius / Скругление | `rounded-2xl` |
| Shadow (md) / Тень | `shadow-xl` |
| Shadow (hover) / Тень наведения | `hover:shadow-2xl` |
| Heading font / Заголовки | `font-bold tracking-tight` |
| Body font / Основной текст | `font-sans leading-relaxed` |
| Type scale / Масштаб текста | `text-6xl md:text-8xl` / `text-4xl md:text-5xl` / `text-lg md:text-xl` |
| Spacing / Отступы | `py-0` · `px-6 md:px-12` · `p-8 md:p-12` |
| Gap / Промежутки | `gap-8` |
| Transition / Переходы | `transition-all duration-300` |
| Active / Активное состояние | `active:scale-95` |

#### Never use in this style / Нельзя в этом стиле

- EN: `bg-scroll` — requires fixed backgrounds for depth effect
- RU: `bg-scroll` — обязателен фиксированный фон для эффекта глубины
- EN: `rounded-none`
- RU: `rounded-none` (запрещено)
- EN: `shadow-none`
- RU: `shadow-none` (запрещено)

#### Do / Правила

- EN: Use `bg-fixed` to create fixed background parallax effect
- RU: Используй `bg-fixed` для эффекта параллакса фиксированного фона
- EN: Each section uses `min-h-screen` full-screen height
- RU: Каждая секция — `min-h-screen`, полноэкранная высота
- EN: Content areas use semi-transparent backgrounds `bg-white/90` for readability
- RU: Контент — на полупрозрачных подложках `bg-white/90` для читаемости
- EN: Use `sticky top-0` for sticky scroll effects
- RU: Используй `sticky top-0` для эффектов прилипания при скролле
- EN: Background images use `bg-cover bg-center`
- RU: Фоновые изображения — `bg-cover bg-center`
- EN: Transition sections use gradient or blur effects
- RU: Секции-переходы — с градиентами или блюром
- EN: Interactions prioritize opacity and blur changes (depth of field), avoiding large displacements that cause dizziness
- RU: Взаимодействия приоритезируют opacity/blur (глубина резкости), избегай крупных перемещений, вызывающих «укачивание»
- EN: Slow sweep light layers (Glass Glare) on cards for lens reflection feel
- RU: Медленные блики-слой на карточках (Glass Glare) для ощущения объектива
- EN: Longer easing `duration-500/700` for cinematic narrative rhythm
- RU: Длинный easing `duration-500/700` для кинематографичного ритма

#### Don't / Запреты

- EN: No insufficient contrast between background images and content
- RU: Контраст фоновых картинок и контента не должен быть слабым
- EN: No inconsistent section heights that break rhythm
- RU: Не ломай ритм разными высотами секций
- EN: No excessive parallax layers causing performance issues
- RU: Не перегружай параллакс-слоями (производительность)
- EN: No ignoring mobile parallax degradation handling
- RU: Не забывай деградацию параллакса на мобильных
- EN: No overly dense content that breaks focus
- RU: Не перегружай контент — фокус должен сохраняться
- EN: No large vertical card hover jumps (background already moves; foreground restrained)
- RU: Без крупных вертикальных скачков карточек на hover (фон уже движется)
- EN: No short, abrupt animations (breaks immersive narrative)
- RU: Никаких коротких резких анимаций (ломают иммерсивность)

---

## 3. Shader Gradient (着色器渐变)

### EN
A premium SaaS aesthetic built on a real-time WebGL fragment-shader mesh gradient. A slowly breathing iridescent field flows across a near-black canvas while frosted-glass panels float above it, paired with a clean modern sans and a single bright accent — the living-gradient look of Stripe, Linear, and Vercel heroes.

### RU
Премиум-эстетика SaaS на базе живого WebGL-градиента (fragment shader). Медленно «дышащее» переливающееся поле течёт по почти чёрному холсту, над ним парят панели из матового стекла; чистый современный sans и один яркий акцент — «живой» градиент в духе героев Stripe, Linear и Vercel.

| Token | Value / Значение |
| --- | --- |
| Primary / Основной | `#08090D` |
| Secondary / Вторичный | `#EDEEF2` |
| Accent 1 / Акцент 1 | `#7C5CFF` |
| Accent 2 / Акцент 2 | `#22D3EE` |
| Accent 3 / Акцент 3 | `#F472B6` |
| Border / Граница | `border border-white/10` |
| Radius / Скругление | `rounded-2xl` |
| Shadow (md) / Тень | `shadow-[0_20px_60px_rgba(0,0,0,0.45)]` |
| Shadow (hover) / Тень наведения | `hover:shadow-[0_24px_70px_rgba(124,92,255,0.25)]` |
| Heading font / Заголовки | `font-semibold text-white tracking-tight` |
| Body font / Основной текст | `text-white/70 leading-relaxed` |
| Type scale / Масштаб текста | `text-5xl md:text-7xl` / `text-3xl md:text-4xl` / `text-base md:text-lg` |
| Spacing / Отступы | `py-24 md:py-32` · `px-6 md:px-8` · `p-6` |
| Gap / Промежутки | `gap-8` |
| Transition / Переходы | `transition-all duration-300 ease-out` |
| Active / Активное состояние | `active:scale-[0.98]` |

#### Never use in this style / Нельзя в этом стиле

- EN: `bg-gradient-to-r` — motion and color come from the WebGL shader, not decorative CSS gradients
- RU: `bg-gradient-to-r` — движение и цвет даёт WebGL-шейдер, а не декоративные CSS-градиенты
- EN: `from-indigo-600` — stops like this make a cheap AI-cliche gradient; the field is a real fbm shader over near-black
- RU: `from-indigo-600` — стоп-цвета-клише; поле — настоящий fbm-шейдер на почти чёрном
- EN: `via-purple-600`
- RU: `via-purple-600` (запрещено)
- EN: `to-pink-500`
- RU: `to-pink-500` (запрещено)
- EN: `animate-pulse` — do not fake life with CSS keyframes; the living quality is the real shader
- RU: `animate-pulse` — не имитируй «живость» CSS-анимациями; живость — это настоящий шейдер
- EN: `duration-100` — the living gradient is calm and slow; snappy transitions break the premium feel
- RU: `duration-100` — градиент медленный и спокойный; резкие переходы ломают премиальность

#### Do / Правила

- EN: Drive the flowing gradient with a real WebGL fragment shader: full-screen quad + time/resolution uniforms + fbm domain warp
- RU: Градиент — настоящий WebGL fragment shader: полноэкранный quad, uniforms time/resolution, fbm domain warp
- EN: Cap `devicePixelRatio` at 2 and re-size canvas/viewport on resize
- RU: Ограничивай `devicePixelRatio` двойкой; пересчитывай размер канваса и viewport при resize
- EN: Pause requestAnimationFrame offscreen and resume in view via IntersectionObserver
- RU: Ставь rAF на паузу вне экрана и возобновляй через IntersectionObserver
- EN: Under `prefers-reduced-motion` render exactly one static frame, never start the loop
- RU: При `prefers-reduced-motion` — ровно один статичный кадр, без цикла анимации
- EN: When WebGL is unavailable, fall back to a visually similar static CSS gradient background
- RU: Без WebGL — фолбэк на статичный CSS-градиент той же палитры
- EN: Sit content on `backdrop-blur` frosted-glass panels with 1px `white/10` border and a dark scrim for 4.5:1
- RU: Контент — на матовых стеклянных панелях `backdrop-blur` с рамкой 1px `white/10` и тёмной подложкой для контраста 4.5:1
- EN: Near-black `#08090D` base, iridescent gradient, single violet `#7C5CFF` UI accent
- RU: Почти чёрная база `#08090D`, переливающийся градиент, единственный UI-акцент — фиолетовый `#7C5CFF`
- EN: Restrict every DOM animation to transform/opacity — leave the animation budget to the shader
- RU: DOM-анимации только transform/opacity — бюджет отдаётся шейдеру
- EN: `aria-hidden` decorative canvas, explicit size to prevent CLS, content layer independent of canvas
- RU: Декоративный канвас — `aria-hidden`, явные размеры против CLS, слой контента независим от канваса

#### Don't / Запреты

- EN: Never fake a real-time shader with a static gradient PNG or a CSS keyframe animation (the root of cheapness)
- RU: Никогда не имитируй живой шейдер статичной PNG-подложкой или CSS-анимацией (источник «дешевизны»)
- EN: Never skip a devicePixelRatio cap (pixel blowup, dropped frames on retina)
- RU: Не пропускай ограничение devicePixelRatio (пиксельный раздув, дропы кадров на retina)
- EN: Never keep the rAF loop running while offscreen
- RU: Не гоняй rAF-цикл, пока канвас вне экрана
- EN: Never ignore prefers-reduced-motion or omit the WebGL-unavailable fallback
- RU: Не игнорируй prefers-reduced-motion и не выкидывай фолбэк без WebGL
- EN: Never place text directly on the gradient field with no glass panel/scrim (fails contrast)
- RU: Никогда не клади текст прямо на градиент (без стеклянной панели/подложки)
- EN: Never fill the screen with multiple canvases or multiple loud accents
- RU: Не заполняй экран несколькими канвасами и множеством громких акцентов
- EN: Never animate DOM element position/shadow and steal the shader's GPU budget
- RU: Не анимируй позицию/тень DOM-элементов — не отбирай GPU-бюджет у шейдера

---

## 4. Apple Liquid Glass (Apple 流动玻璃)

### EN
Apple's revolutionary design language from WWDC 2025, creating an organic, fluid visual experience beyond traditional frosted glass through SVG refraction filters, rainbow edge halos, fluid morphing animations, and multi-layer glass stacking.

### RU
Революционный язык Apple с WWDC 2025: органичное, текучее визуальное впечатление за пределами обычного «матового стекла» — через SVG-фильтры преломления, радужные ореолы по краям, плавные морф-анимации и многослойное стекло.

| Token | Value / Значение |
| --- | --- |
| Primary / Основной | `rgba(255, 255, 255, 0.1)` |
| Secondary / Вторичный | `rgba(255, 255, 255, 0.15)` |
| Accent 1 / Акцент 1 | `#ff6b6b` |
| Accent 2 / Акцент 2 | `#4ecdc4` |
| Accent 3 / Акцент 3 | `#a855f7` |
| Accent 4 / Акцент 4 | `#007AFF` |
| Accent 5 / Акцент 5 | `#FF2D55` |
| Border / Граница | `border border-white/20` |
| Radius / Скругление | `rounded-[24px]` |
| Shadow (md) / Тень | `shadow-xl shadow-black/10` |
| Shadow (hover) / Тень наведения | `hover:shadow-xl hover:shadow-black/15` |
| Heading font / Заголовки | `font-black bg-gradient-to-r from-[#a855f7] via-[#ff2d92] to-[#a855f7] bg-clip-text text-transparent` |
| Body font / Основной текст | `text-white/80` |
| Type scale / Масштаб текста | `text-5xl md:text-7xl lg:text-8xl` / `text-3xl md:text-4xl` / `text-sm md:text-base` |
| Spacing / Отступы | `py-16 md:py-24` · `px-6 md:px-8` · `p-6 md:p-8` |
| Gap / Промежутки | `gap-6` |
| Transition / Переходы | `transition-all duration-500 ease-out` |
| Active / Активное состояние | `active:scale-[0.98]` |

#### Never use in this style / Нельзя в этом стиле

- EN: `rounded-none` / `rounded-sm` / `rounded` — Liquid Glass requires large rounded corners (`rounded-[24px]` or `rounded-3xl`)
- RU: `rounded-none` / `rounded-sm` / `rounded` — обязательны большие скругления (`rounded-[24px]` или `rounded-3xl`)
- EN: `bg-white` / `bg-black` / `bg-gray-100` / `bg-gray-900` — only semi-transparent backgrounds (`bg-white/10` to `bg-white/15`)
- RU: `bg-white` / `bg-black` / `bg-gray-100` / `bg-gray-900` — только полупрозрачные фоны (`bg-white/10`…`bg-white/15`)
- EN: `shadow-[0px_0px_0px`
- RU: `shadow-[0px_0px_0px` (нулевые тени запрещены)
- EN: `backdrop-blur-sm` / `backdrop-blur` — requires high blur (`backdrop-blur-[40px]` or `backdrop-blur-3xl`)
- RU: `backdrop-blur-sm` / `backdrop-blur` — нужен сильный блюр (`backdrop-blur-[40px]` или `backdrop-blur-3xl`)

#### Do / Правила

- EN: Hero titles use thick stroke `-webkit-text-stroke: 3px #4ecdc4`
- RU: Заголовки hero — толстый обвод `-webkit-text-stroke: 3px #4ecdc4`
- EN: Hero titles use 3D offset shadow `text-shadow: 4px 4px 0 rgba(0,0,0,0.5)`
- RU: Заголовки hero — 3D-офсетная тень `text-shadow: 4px 4px 0 rgba(0,0,0,0.5)`
- EN: Hero titles use gradient fill `bg-gradient-to-r from-[#a855f7] via-[#ff2d92] to-[#a855f7]`
- RU: Заголовки hero — градиентная заливка `from-[#a855f7] via-[#ff2d92] to-[#a855f7]`
- EN: Subtitles use cyan glow `text-shadow: 0 0 20px rgba(78, 205, 196, 0.8)`
- RU: Подзаголовки — голубое свечение `text-shadow: 0 0 20px rgba(78, 205, 196, 0.8)`
- EN: Ultra-high blur `backdrop-blur-[40px]` or `backdrop-blur-3xl`
- RU: Сверхсильный блюр `backdrop-blur-[40px]` или `backdrop-blur-3xl`
- EN: Saturation boost `backdrop-saturate-[1.8]` or `backdrop-saturate-200`
- RU: Усиление насыщенности `backdrop-saturate-[1.8]` или `backdrop-saturate-200`
- EN: Rainbow gradient borders simulate light refraction
- RU: Радужные градиентные рамки имитируют преломление света
- EN: Extra-large corners `rounded-3xl` / `rounded-[24px]`; fluid transitions `duration-500 ease-out`
- RU: Очень большие скругления `rounded-3xl`/`rounded-[24px]`; «текучие» переходы `duration-500 ease-out`

#### Don't / Запреты

- EN: No plain white titles (must use gradient + thick stroke + 3D shadow)
- RU: Никаких просто белых заголовков (обязательно градиент + толстый обвод + 3D-тень)
- EN: No omitting the 3D offset shadow (`4px 4px` is mandatory)
- RU: Не выкидывай 3D-офсетную тень (`4px 4px` обязательны)
- EN: No thin strokes (hero must be 3px, h1/h2 at least 2px)
- RU: Никаких тонких обводов (hero — 3px, h1/h2 — минимум 2px)
- EN: No omitting text glow effects
- RU: Не выкидывай свечение текста
- EN: No low blur values (`backdrop-blur-sm` — too weak)
- RU: Никаких слабых значений блюра (`backdrop-blur-sm` — слишком слабо)
- EN: No omitting saturation enhancement (colors dull)
- RU: Не выкидывай усиление насыщенности (цвета тускнеют)
- EN: No right angles or small corners (`rounded-none`, `rounded-sm`)
- RU: Никаких прямых углов и мелких скруглений (`rounded-none`, `rounded-sm`)
- EN: No fast transitions (`duration-100`, `duration-150`)
- RU: Никаких быстрых переходов (`duration-100`, `duration-150`)

---

## 5. Paper Craft (纸艺手作)

### EN
Paper craft and paper-cut style with layered paper effects, soft shadows suggesting depth, and handmade textured edges. Ideal for children's brands, educational products, and creative studios.

### RU
Бумажный стиль «papercut»: слоистые бумажные эффекты, мягкие тени с ощущением глубины, рукотворные текстурные края. Идеален для детских брендов, образовательных продуктов и креативных студий.

| Token | Value / Значение |
| --- | --- |
| Primary / Основной | `#e85d75` |
| Secondary / Вторичный | `#fdf6ee` |
| Accent 1 / Акцент 1 | `#5cb8a5` |
| Accent 2 / Акцент 2 | `#f5c040` |
| Accent 3 / Акцент 3 | `#6b7fb5` |
| Accent 4 / Акцент 4 | `#81a7e2` |
| Border / Граница | `border-2 border-[#e0d8cc]` |
| Radius / Скругление | `rounded-xl` |
| Shadow (md) / Тень | `shadow-[4px_4px_0px_rgba(0,0,0,0.08)]` |
| Shadow (hover) / Тень наведения | `hover:shadow-[5px_5px_0px_rgba(0,0,0,0.12)]` |
| Heading font / Заголовки | `font-bold` |
| Body font / Основной текст | `font-sans` |
| Type scale / Масштаб текста | `text-4xl md:text-6xl lg:text-7xl` / `text-2xl md:text-3xl` / `text-sm md:text-base` |
| Spacing / Отступы | `py-12 md:py-20` · `px-4 md:px-8` · `p-6` |
| Gap / Промежутки | `gap-6` |
| Transition / Переходы | `transition-all duration-200` |
| Active / Активное состояние | `active:translate-y-0.5 active:shadow-[1px_1px_0px_rgba(0,0,0,0.06)]` |

#### Never use in this style / Нельзя в этом стиле

- EN: `bg-black` / `bg-gray-900` / `bg-gray-950` — warm light backgrounds only, never dark
- RU: `bg-black` / `bg-gray-900` / `bg-gray-950` — только тёплый светлый фон, никакого тёмного
- EN: `shadow-[0_0_` — use offset paper shadows, not glows
- RU: `shadow-[0_0_` — только офсетные «бумажные» тени, не свечения
- EN: `text-cyan-` / `text-fuchsia-` / `bg-cyan-` / `bg-fuchsia-` — craft colors only, not neon
- RU: `text-cyan-` / `text-fuchsia-` / `bg-cyan-` / `bg-fuchsia-` — только ремесленные цвета, без неона

#### Do / Правила

- EN: Paper white `bg-[#fdf6ee]` or soft warm white for backgrounds
- RU: Фоны — «бумажно-белые» `bg-[#fdf6ee]` или мягкий тёплый белый
- EN: Cards use paper shadows `shadow-[4px_4px_0px_rgba(0,0,0,0.08)]` to simulate raised paper
- RU: Карточки — «бумажные» тени `shadow-[4px_4px_0px_rgba(0,0,0,0.08)]`, будто лист приподнят
- EN: Buttons use offset shadows `shadow-[3px_3px_0px_rgba(0,0,0,0.1)]`
- RU: Кнопки — офсетные тени `shadow-[3px_3px_0px_rgba(0,0,0,0.1)]` (бумажная деталь приподнялась)
- EN: Rounded but imperfect corners `rounded-xl` + slight rotation `rotate-[1deg]`
- RU: Скруглённые, но неровные углы `rounded-xl` + лёгкий поворот `rotate-[1deg]`
- EN: Bright craft colors `bg-[#e85d75]`, `bg-[#5cb8a5]`, `bg-[#f5c040]`
- RU: Яркие ремесленные цвета `bg-[#e85d75]`, `bg-[#5cb8a5]`, `bg-[#f5c040]`
- EN: Text `text-[#2d2d2d]` with handwritten-feel or rounded sans-serif fonts
- RU: Текст `text-[#2d2d2d]`, шрифты с «рукописным» характером или округлый sans-serif
- EN: Layering via multiple absolutely-positioned divs with different shadow depths
- RU: Слои — несколько div-ов абсолютным позиционированием и разной глубиной теней
- EN: Hover slightly lifts: `hover:-translate-y-1 hover:shadow-[5px_5px_0px_rgba(0,0,0,0.12)]`
- RU: Hover слегка приподнимает: `hover:-translate-y-1 hover:shadow-[5px_5px_0px_rgba(0,0,0,0.12)]`
- EN: Multi-layer cards fan bottom paper layers apart on hover (Layer Separation)
- RU: У многослойных карточек нижние слои «раскрываются веером» на hover (Layer Separation)
- EN: Shadow offset grows in sync with element shift (paper lifts off the surface)
- RU: Смещение тени увеличивается синхронно со сдвигом элемента (бумага отрывается от стола)
- EN: Input focus uses deeper inset shadow — cardboard cutout (Cutout Depth)
- RU: Фокус инпутов — глубокая inset-тень, «прорезь» в картоне (Cutout Depth)

#### Don't / Запреты

- EN: No dark/black backgrounds
- RU: Не используй тёмный/чёрный фон
- EN: No glow effects or neon shadows
- RU: Никаких свечений и неоновых теней
- EN: No metallic textures or glassmorphism
- RU: Никаких металлических текстур и глассморфизма
- EN: No overly precise right-angle edges (looks too digital)
- RU: Никаких слишком точных прямых углов (слишком «цифрово»)
- EN: No high-saturation fluorescent colors
- RU: Никаких кислотных флуоресцентных цветов
- EN: No gradient glow effects
- RU: Никаких градиентных свечений
- EN: No drop-shadow filters (use box-shadow to simulate paper shadows)
- RU: Никаких drop-shadow-фильтров (имитируй бумажные тени через box-shadow)
- EN: No spring bounce curves (paper is light but not rubbery)
- RU: Никаких «пружинных» кривых (бумага лёгкая, но не резиновая)
- EN: No layered pieces moving in one direction on hover (loses handmade peeling feel)
- RU: Слои не должны ехать в одну сторону на hover (теряется ощущение ручного отслоения)

---

## 6. Bento Grid (便当盒布局)

### EN
Irregular grid layout inspired by Japanese bento boxes, creating visual hierarchy through varied card sizes. Commonly used for portfolios and product showcases.

### RU
Неровная сетка по мотивам японских бенто-боксов: визуальная иерархия через разные размеры карточек. Часто используется для портфолио и витрин продукта.

| Token | Value / Значение |
| --- | --- |
| Primary / Основной | `#18181b` |
| Secondary / Вторичный | `#fafafa` |
| Accent 1 / Акцент 1 | `#3b82f6` |
| Accent 2 / Акцент 2 | `#8b5cf6` |
| Accent 3 / Акцент 3 | `#ec4899` |
| Accent 4 / Акцент 4 | `#f97316` |
| Border / Граница | `border border-zinc-100 dark:border-zinc-800` |
| Radius / Скругление | `rounded-2xl` |
| Shadow (md) / Тень | `shadow-md` |
| Shadow (hover) / Тень наведения | `hover:shadow-md hover:-translate-y-0.5` |
| Heading font / Заголовки | `font-semibold text-zinc-900 dark:text-zinc-100` |
| Body font / Основной текст | `text-zinc-600 dark:text-zinc-400` |
| Type scale / Масштаб текста | `text-4xl md:text-5xl lg:text-6xl` / `text-2xl md:text-3xl` / `text-sm md:text-base` |
| Spacing / Отступы | `py-12 md:py-16 lg:py-20` · `px-4 md:px-6 lg:px-8` · `p-4 md:p-6` |
| Gap / Промежутки | `gap-4 md:gap-6` |
| Transition / Переходы | `transition-all duration-200` |
| Active / Активное состояние | `active:scale-95` |

#### Never use in this style / Нельзя в этом стиле

- EN: `rounded-none` / `rounded-sm` — requires rounded corners (`rounded-xl`, `rounded-2xl`, `rounded-3xl`)
- RU: `rounded-none` / `rounded-sm` — обязательны скругления (`rounded-xl`/`rounded-2xl`/`rounded-3xl`)
- EN: `gap-1` / `gap-2` / `gap-10` / `gap-12` — consistent medium gaps (`gap-4`/`gap-6`)
- RU: `gap-1` / `gap-2` / `gap-10` / `gap-12` — единые средние отступы (`gap-4`/`gap-6`)

#### Do / Правила

- EN: CSS Grid layout `grid grid-cols-4`
- RU: CSS Grid: `grid grid-cols-4`
- EN: Cards span multiple rows/columns `col-span-2`, `row-span-2`
- RU: Карточки «растягиваются» на несколько строк/столбцов: `col-span-2`, `row-span-2`
- EN: Consistent gaps `gap-4`/`gap-6`; rounded corners `rounded-xl`/`rounded-2xl`
- RU: Единые отступы `gap-4`/`gap-6`; скругления `rounded-xl`/`rounded-2xl`
- EN: Primary content in large cards, secondary in small
- RU: Главный контент — в крупных карточках, второстепенный — в мелких
- EN: Use aspect-ratio to maintain proportions
- RU: Используй aspect-ratio для пропорций карточек
- EN: Smooth hover lift + micro-scale `hover:-translate-y-1 hover:scale-[1.01]`
- RU: Плавный hover-подъём с микро-скейлом `hover:-translate-y-1 hover:scale-[1.01]`
- EN: Shadow expands compact → wide on hover (`shadow-sm` → `shadow-xl`)
- RU: Тень на hover расширяется от компактной к широкой (`shadow-sm` → `shadow-xl`)
- EN: Inner icons change color / `scale-110` on `group-hover`
- RU: Иконки внутри карточек реагируют на `group-hover` (цвет / `scale-110`)
- EN: Spring-like easing `ease-out`, `duration-200`–`300`
- RU: Пружинный easing `ease-out`, `duration-200`–`300`

#### Don't / Запреты

- EN: Do not make all cards same size (loses bento character)
- RU: Не делай все карточки одного размера (теряется «бенто»-суть)
- EN: Do not use inconsistent gaps
- RU: Не смешивай разные отступы
- EN: Do not overcrowd cards without whitespace
- RU: Не набивай карточки без воздуха
- EN: Do not ignore responsive adaptation
- RU: Не игнорируй адаптив
- EN: Do not cram too much content inside cards
- RU: Не перегружай содержимое карточек
- EN: Do not use hard-edge shadows (`shadow-[Xpx_Ypx_0px]`)
- RU: Никаких жёстких ступенчатых теней (`shadow-[Xpx_Ypx_0px]`)
- EN: Do not use sharp corners (rounded corners required)
- RU: Никаких острых углов (скругления обязательны)

---

## 7. Fullscreen Hero (全屏英雄区)

### EN
A hero section layout with fullscreen image or video background that captures attention through stunning visuals. Ideal for brand showcases, product launches, and event promotions.

### RU
Hero-секция с полноэкранным фоном (фото или видео), держащая внимание эффектной картинкой. Идеально для брендов, запусков продукта и промо-событий.

| Token | Value / Значение |
| --- | --- |
| Primary / Основной | `#ffffff` |
| Secondary / Вторичный | `#000000` |
| Accent 1 / Акцент 1 | `#ff6b6b` |
| Accent 2 / Акцент 2 | `#4ecdc4` |
| Accent 3 / Акцент 3 | `#ffe66d` |
| Accent 4 / Акцент 4 | `#6c5ce7` |
| Border / Граница | `border-2 border-white` |
| Radius / Скругление | `rounded-full` |
| Shadow (md) / Тень | `shadow-none` |
| Shadow (hover) / Тень наведения | `shadow-none` |
| Heading font / Заголовки | `font-bold leading-tight` |
| Body font / Основной текст | `font-sans` |
| Type scale / Масштаб текста | `text-5xl md:text-7xl lg:text-8xl` / `text-3xl md:text-5xl` / `text-lg md:text-xl lg:text-2xl` |
| Spacing / Отступы | `py-0` · `px-4 md:px-6 lg:px-8` · `p-8 md:p-10` |
| Gap / Промежутки | `gap-4 md:gap-6` |
| Transition / Переходы | `transition-all duration-300` |
| Active / Активное состояние | `active:scale-95` |

#### Never use in this style / Нельзя в этом стиле

- EN: `shadow-sm` / `shadow-md` / `shadow-lg` / `shadow-xl` — uses overlays and contrast instead of shadows
- RU: `shadow-sm` / `shadow-md` / `shadow-lg` / `shadow-xl` — вместо теней используются overlay-слои и контраст
- EN: `bg-zinc-50` / `bg-gray-50` / `text-zinc-900` / `text-gray-900` / `border-gray-200` / `border-zinc-200`
- RU: `bg-zinc-50` / `bg-gray-50` / `text-zinc-900` / `text-gray-900` / `border-gray-200` / `border-zinc-200` (светлые серые темы запрещены)

#### Do / Правила

- EN: `h-screen`/`min-h-screen` for fullscreen coverage; `object-cover` on images
- RU: `h-screen`/`min-h-screen` для полного покрытия; `object-cover` у картинок
- EN: Gradient or semi-transparent overlays to ensure text readability
- RU: Градиентные/полупрозрачные затемнения для читаемости текста
- EN: Content positioned absolutely or centered with flex
- RU: Контент — абсолютным позиционированием или центрированием через flex
- EN: Provide scroll indicators to guide users downward
- RU: Добавь индикатор скролла вниз
- EN: Video backgrounds muted and autoplay; provide image fallback
- RU: Видео-фон — без звука, autoplay; обязательно фолбэк на картинку
- EN: Primary CTA `hover:-translate-y-1` + `hover:shadow-[0_8px_28px_rgba(0,0,0,0.5)]` (gravity float)
- RU: Основная CTA: `hover:-translate-y-1` + `hover:shadow-[0_8px_28px_rgba(0,0,0,0.5)]` (парение)
- EN: Feature cards `group` + `hover:-translate-y-2` + `hover:shadow-[0_16px_40px_rgba(0,0,0,0.5)]`; icon container `group-hover:scale-110`
- RU: Карточки фич: класс `group` + `hover:-translate-y-2` + `hover:shadow-[0_16px_40px_rgba(0,0,0,0.5)]`; иконка — `group-hover:scale-110`
- EN: All buttons `active:scale-[0.98] active:translate-y-0` + `focus:ring-2 focus:ring-white/80 focus:ring-offset-2`
- RU: У всех кнопок `active:scale-[0.98] active:translate-y-0` + `focus:ring-2 focus:ring-white/80 focus:ring-offset-2`

#### Don't / Запреты

- EN: Do NOT place text directly on complex backgrounds without an overlay
- RU: Никогда не клади текст на сложный фон без затемнения
- EN: Do NOT use low-quality or stretched images
- RU: Не используй плохие/растянутые картинки
- EN: Do NOT ignore mobile responsiveness
- RU: Не игнорируй мобильную адаптацию
- EN: Do NOT fill the entire space with content and no whitespace
- RU: Не забивай весь экран контентом без «воздуха»
- EN: Do NOT autoplay video with sound
- RU: Не автовоспроизводи видео со звуком
- EN: Do NOT omit `active:scale-[0.98]` on buttons (tactile confirmation feels terrible otherwise)
- RU: Не опускай `active:scale-[0.98]` у кнопок (без тактильного отклика кнопки «мертвые»)
- EN: Do NOT omit `group` class on cards (icon micro-interaction depends on it)
- RU: Не забывай класс `group` у карточек (микроанимация иконки завязана на него)

---

## 8. Dopamine Design (多巴胺设计)

### EN
High-saturation neon palette, bold typography, energizing visual punch. 2025–2026 design trend: colors directly stimulate dopamine, making the interface feel like joy and excitement.

### RU
Высоконасыщенные неоновые цвета, жирная типографика, энергия в каждом пикселе. Тенденция 2025–2026: цвет напрямую стимулирует дофамин — интерфейс радостный и возбуждающий.

| Token | Value / Значение |
| --- | --- |
| Primary / Основной | `#ff006e` |
| Secondary / Вторичный | `#8338ec` |
| Accent 1 / Акцент 1 | `#ffbe0b` |
| Accent 2 / Акцент 2 | `#3a86ff` |
| Accent 3 / Акцент 3 | `#06d6a0` |
| Accent 4 / Акцент 4 | `#fb5607` |
| Border / Граница | `border-2 border-[#ff006e]/20` |
| Radius / Скругление | `rounded-3xl` |
| Shadow (md) / Тень | `shadow-[0_8px_30px_rgba(255,0,110,0.4)]` |
| Shadow (hover) / Тень наведения | `hover:shadow-[0_12px_40px_rgba(255,0,110,0.6)]` |
| Heading font / Заголовки | `font-sans font-black tracking-tight` |
| Body font / Основной текст | `font-sans text-base font-medium` |
| Type scale / Масштаб текста | `text-5xl md:text-7xl font-black tracking-tight leading-[0.95]` / `text-xl md:text-2xl font-bold` / `text-base font-medium` |
| Spacing / Отступы | `py-16 md:py-24` · `px-6 md:px-8` · `p-6 md:p-8` |
| Gap / Промежутки | `gap-6` |
| Transition / Переходы | `transition-all duration-300` |
| Active / Активное состояние | `active:scale-95` |

#### Never use in this style / Нельзя в этом стиле

- EN: `text-gray-500` / `text-gray-400` / `text-gray-300` / `bg-gray-100` / `bg-gray-50` / `bg-gray-200` — no large gray areas
- RU: `text-gray-500` / `text-gray-400` / `text-gray-300` / `bg-gray-100` / `bg-gray-50` / `bg-gray-200` — никаких больших серых зон
- EN: `shadow-sm` / `shadow-md` / `shadow-lg` / `shadow-xl` — colored shadows only (pink, purple, blue glows)
- RU: `shadow-sm` / `shadow-md` / `shadow-lg` / `shadow-xl` — только цветные тени (розовые, фиолетовые, синие свечения)

#### Do / Правила

- EN: High-saturation colors `bg-[#ff006e] bg-[#8338ec] bg-[#ffbe0b] bg-[#3a86ff]`
- RU: Высоконасыщенные цвета `bg-[#ff006e] bg-[#8338ec] bg-[#ffbe0b] bg-[#3a86ff]`
- EN: Maximum radius `rounded-full rounded-3xl rounded-2xl`
- RU: Максимальные скругления `rounded-full rounded-3xl rounded-2xl`
- EN: Oversized headings `text-5xl md:text-7xl font-black`
- RU: Гигантские заголовки `text-5xl md:text-7xl font-black`
- EN: Pill-shaped buttons `rounded-full px-8`
- RU: Кнопки-пилюли `rounded-full px-8`
- EN: Colored shadows `shadow-[0_8px_30px_rgba(255,0,110,0.4)]`
- RU: Цветные тени `shadow-[0_8px_30px_rgba(255,0,110,0.4)]`
- EN: Gradient backgrounds `bg-gradient-to-br from-pink-500 via-purple-500 to-blue-500`
- RU: Градиентные фоны `bg-gradient-to-br from-pink-500 via-purple-500 to-blue-500`
- EN: Bouncy hover `hover:scale-105 transition-transform`
- RU: Упругий hover `hover:scale-105 transition-transform`
- EN: Sprinkle emojis and playful icons
- RU: Добавляй эмодзи и игривые иконки

#### Don't / Запреты

- EN: No large gray areas (`text-gray-500 bg-gray-100`)
- RU: Никаких больших серых зон (`text-gray-500 bg-gray-100`)
- EN: No desaturated/pastel colors
- RU: Никаких десатурированных/пастельных цветов
- EN: No small border-radius (`rounded-sm`, `rounded-md`)
- RU: Никаких мелких скруглений (`rounded-sm`, `rounded-md`)
- EN: No serious/corporate typography
- RU: Никакой серьёзной «корпоративной» типографики
- EN: No serif fonts
- RU: Никаких serif-шрифтов
- EN: No black/gray shadows (`shadow-lg`)
- RU: Никаких чёрных/серых теней (`shadow-lg`)
