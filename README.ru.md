🌐 **Language / Язык:** [English](README.md) | [Русский](#)

## О проекте

HyperHDR — это система фоновой подсветки с открытым исходным кодом для телевизоров и музыкальных систем, основанная на анализе видео и аудио потоков в реальном времени. Проект разработан с акцентом на стабильность, высокую производительность и превосходное качество изображения. Оптимизированная для однопоточной и многопоточной обработки видео, HyperHDR работает без проблем на **Windows**, **macOS** (x64/arm64: M1, M2) и **Linux x64 и ARM** (включая Raspberry Pi).

![v20](https://github.com/awawa-dev/HyperHDR/assets/69086569/9bc7999d-1515-4a96-ba5e-8a732cf7d8a4)

## Основные возможности HyperHDR

В основе HyperHDR лежит **Infinite Color Engine** — собственный конвейер рендеринга, разработанный для максимальной точности и визуальной достоверности. Используя обработку с плавающей точкой, он создает более плавные градиенты, устраняет артефакты округления и обеспечивает стабильные и последовательные цветовые преобразования. В то время как многие другие решения полагаются на базовые 24-битные цветовые операции, которые приводят к потере точности и видимым полосам, Infinite Color Engine достигает безупречной точности и профессионального качества результатов. Благодаря поддержке глубокого цвета для устройств Philips Hue и HD108, HyperHDR обеспечивает более насыщенное и яркое освещение, чем когда-либо прежде. ( :new: HyperHDR v22)

### Ключевые преимущества Infinite Color Engine:
* **Точность с плавающей точкой:** Все цветовые вычисления используют высокоточную арифметику с плавающей точкой, устраняя накопленные ошибки округления для более точных результатов
* **Точность линейного sRGB:** Основные цветовые преобразования обрабатываются в линейном пространстве sRGB, обеспечивая физически правильное и последовательное воспроизведение света
* **Поддержка глубокого цвета:** Совместимые устройства, включая лампы Philips Hue, Lifx и светодиоды HD108, могут использовать рендеринг за пределами стандартной 24-битной глубины цвета RGB
* **Усовершенствованные алгоритмы сглаживания цвета:** интерполяторы на основе инерционной физики, экспоненциальные и перцептивно-единообразные YUV/RGB для более плавных и естественных переходов цвета

### Дополнительные функции:
* **Сверхнизкое использование процессора** на SoC типа Raspberry Pi или Intel N100
* **Легковесный дизайн** без тяжелых зависимостей (например, Python, Java)
* **Низкая задержка обработки видео** для светодиодных лент и ламп
* **Оптимизированная многопоточность**, позволяющая Raspberry Pi обрабатывать видеопотоки высокого качества
* **Высокая портативность** на встроенных платформах на базе ARM
* **Системная диагностика:** использование процессора/оперативной памяти в реальном времени, температура процессора, обнаружение пониженного напряжения, производительность USB-граббера и светодиодов
* **Поддержка USB-граббера** для Linux, Windows 10/11 и macOS для P010/NV12/YUYV/MJPEG/UYVY/I420/RGB
* **Аппаратно-ускоренный захват:** PipeWire/Portal (Linux/Wayland), DirectX (Windows 10/11)
* **Захват экрана DirectX с поддержкой HDR:** Поддерживает DXGI_FORMAT_R16G16B16A16_FLOAT и несколько мониторов
* **Оптимизированная обработка видео:** Наш оптимизированный конвейер плавно обрабатывает 1080p **P010**/**NV12**/**YUYV** даже на Rpi4
* **Встроенная визуализация аудио** на основе спектрального анализа
* **Поддержка MQTT** для интеграции IoT
* **Интеграция с Home Assistant и zigbee2mqtt**
* **Автоматическое тональное отображение** для SDR/HDR контента
* **Автоматическая калибровка LUT** для оптимального качества HDR/SDR граббера с использованием тестовых файлов MP4
* **Тестирование задержки** для USB-грабберов
* **Поддержка P010** для Windows, Linux: наш пропатченный образ Raspberry Pi OS (P010 не поддерживается в основной версии ОС)
* **Интуитивный редактор светодиодных лент** с автоматическим или ручным редактированием геометрии с помощью мыши и контекстных меню
* **Умное обнаружение сигнала** с адаптивным обучением для USB-грабберов
* **Расширенная калибровка SK6812 RGBW** для [HyperSerialEsp8266](https://github.com/awawa-dev/HyperSerialEsp8266), [HyperSerialESP32](https://github.com/awawa-dev/HyperSerialESP32), [HyperSPI](https://github.com/awawa-dev/HyperSPI) и [HyperSerialPico](https://github.com/awawa-dev/HyperSerialPico)
* **Поддержка внешнего тонального отображения** для источников flatbuffers/protobuf
* **Широкая совместимость со светодиодными лентами** и для WS281x, APA102, HD107, SK9822, SK6812 наши сверхбыстрые LED-контроллеры:
  * [HyperSPI](https://github.com/awawa-dev/HyperSPI) для ESP8266/ESP32/rp2040
  * [HyperSerialEsp8266](https://github.com/awawa-dev/HyperSerialEsp8266), [HyperSerialESP32](https://github.com/awawa-dev/HyperSerialESP32), [HyperSerialPico](https://github.com/awawa-dev/HyperSerialPico) подключение через USB-порт со скоростью 2Mb+
  * [HyperSerialWLED](https://github.com/awawa-dev/HyperSerialWLED): наш оптимизированный форк WLED с подключением через USB-порт со скоростью 2Mb+

Усовершенствованный видеоконвейер HyperHDR значительно улучшает выходной сигнал светодиодов, создавая более плавное и захватывающее впечатление от фоновой подсветки. Он работает с SDR, HDR и Dolby Vision (LLDV, если поддерживается вашим оборудованием). Вместо использования USB-грабберов вы также можете использовать программный захват экрана непосредственно с вашего ПК.

![example](https://github.com/awawa-dev/HyperHDR/assets/69086569/4077c05d-4c02-47eb-8d64-a334064403b3)

## Загрузки

Официальные релизы:
[https://github.com/awawa-dev/HyperHDR/releases](https://github.com/awawa-dev/HyperHDR/releases)

Официальный репозиторий для Linux:
[https://awawa-dev.github.io/](https://awawa-dev.github.io/)

Последние тестовые сборки (требуется вход в GitHub):
[https://github.com/awawa-dev/HyperHDR/actions](https://github.com/awawa-dev/HyperHDR/actions)

## Руководства и инструкции

[Руководство по установке](https://github.com/awawa-dev/HyperHDR/wiki/Installation)
[Официальная Wiki](https://github.com/awawa-dev/HyperHDR/wiki)
[Полное руководство по созданию системы фоновой подсветки SK6812 RGBW (2023)](https://www.hyperhdr.eu/2023/02/ultimate-guide-on-how-to-build-led.html)

## Сообщество

[Форум поддержки HyperHDR](https://github.com/awawa-dev/HyperHDR/discussions)

## Сборка из исходного кода

[Руководство по компиляции](https://github.com/awawa-dev/HyperHDR/wiki/Compiling-HyperHDR)

## В прессе

<img align="left" width="286" height="200" src="https://i.postimg.cc/zvr9rWR4/magazine.jpg"/>
<a href="https://makezine.com/projects/bright-lights-big-tv-diy-ambient-lights/">Make: Magazine #84 (2023)</a><br>
<a href="https://magpi.raspberrypi.com/issues/117">MagPi #117 (2022)</a><br>
<a href="https://web.archive.org/web/20230824230034/https://www.smartprix.com/bytes/what-is-bias-lighting-philips-hue-ambient-light-vs-govee-dreamview-tv-backlight-vs-diy-ambient-light-with-hyperhdr/">Сравнение современных систем фоновой подсветки (2023)</a><br>
<a href="https://www.raspberrypi.com/tutorials/raspberry-pi-tv-ambient-lighting">Учебное пособие на raspberrypi.com</a><br>
<a href="https://www.youtube.com/watch?v=4jkwFsMkKwU">Создание 4K HDMI подсветки для телевизора (2021)</a><br><br><br><br><br>

## Лицензия

Выпущено под лицензией MIT
[![GitHub license](https://img.shields.io/badge/License-MIT-yellow.svg)](https://raw.githubusercontent.com/awawa-dev/HyperHDR/master/LICENSE)
