# UAS_IMK
Interaksi Manusia dan Komputer
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IMK Quiz</title>
    <link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(to right, #e0f2f7, #c1e0f0); /* Light blue-green pastel gradient */
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            color: #34495e; /* Darker text for light background */
        }

        .container {
            background-color: #ffffff; /* Pure white for a fresh look */
            padding: 30px 40px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15); /* Lighter shadow */
            width: 90%; /* Responsive width */
            max-width: 800px;
            text-align: center;
            position: relative;
            overflow: hidden;
            box-sizing: border-box; /* Include padding in width calculation */
        }

        .container::before {
            content: '';
            position: absolute;
            top: -50px;
            left: -50px;
            width: 150px;
            height: 150px;
            background-color: #a7d9f7; /* Soft pastel blue */
            border-radius: 50%;
            opacity: 0.5; /* Slightly more visible */
            z-index: 0;
        }

        .container::after {
            content: '';
            position: absolute;
            bottom: -50px;
            right: -50px;
            width: 120px;
            height: 120px;
            background-color: #ffd8a7; /* Soft pastel orange */
            border-radius: 50%;
            opacity: 0.5; /* Slightly more visible */
            z-index: 0;
        }

        h1 {
            color: #4a90e2; /* A pleasant blue */
            margin-bottom: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            z-index: 1;
        }

        .question-block {
            background-color: #f0f8ff; /* Very light blue background for questions */
            border-radius: 15px;
            padding: 20px;
            margin-bottom: 20px;
            text-align: left;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1); /* Lighter shadow */
            position: relative;
            z-index: 1;
            color: #34495e; /* Darker text */
            border: 1px solid #e0e0e0; /* Subtle border */
        }

        .question-text {
            font-weight: bold;
            margin-bottom: 15px;
            color: #6a82a0; /* Muted blue for question text */
        }

        .options label {
            display: block;
            margin-bottom: 10px;
            padding: 10px;
            background-color: #f7fcff; /* Lighter option background */
            border-radius: 10px;
            cursor: pointer;
            transition: background-color 0.2s ease, transform 0.2s ease;
            display: flex;
            align-items: center;
            color: #34495e;
            border: 1px solid #e8e8e8; /* Subtle border for options */
        }

        .options label:hover {
            background-color: #e0f2f7; /* Hover effect: slightly darker pastel blue */
            transform: translateY(-2px);
        }

        .options input[type="radio"] {
            margin-right: 10px;
            accent-color: #4a90e2; /* Blue radio button */
        }

        .correct-answer {
            background-color: #d4edda !important; /* Soft green for correct */
            border: 1px solid #c3e6cb;
            font-weight: bold;
            color: #155724; /* Darker green text */
        }

        .wrong-answer {
            background-color: #f8d7da !important; /* Soft red for wrong */
            border: 1px solid #f5c6cb;
            color: #721c24; /* Darker red text */
        }

        .explanation {
            margin-top: 10px;
            padding-top: 10px;
            border-top: 1px dashed #cccccc;
            color: #7f8c8d;
            font-size: 0.9em;
        }

        button {
            background-color: #4a90e2; /* Vibrant blue */
            color: white;
            padding: 12px 25px;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            font-size: 1em;
            margin-top: 20px;
            transition: background-color 0.3s ease, transform 0.3s ease;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.15);
            position: relative;
            z-index: 1;
        }

        button:hover {
            background-color: #387bd6; /* Darker blue on hover */
            transform: translateY(-3px);
        }

        .score-container {
            margin-top: 30px;
            padding: 20px;
            background-color: #e6f7ff; /* Very light blue background for score */
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            position: relative;
            z-index: 1;
            border: 1px solid #d0e7f7; /* Subtle border */
        }

        .score-container h2 {
            color: #4a90e2;
            margin-bottom: 20px;
        }

        #restart-btn {
            background-color: #5cb85c; /* Green for restart */
        }

        #restart-btn:hover {
            background-color: #4cae4c; /* Darker green on hover */
        }

        /* Simple cute icon for general use (e.g., as a separator or bullet) */
        .icon {
            font-family: 'Material Icons';
            font-size: 1.2em;
            vertical-align: middle;
            margin-right: 5px;
            color: #f7cf6e; /* Soft yellow accent */
        }

        /* Responsive adjustments for smaller screens */
        @media (max-width: 768px) {
            .container {
                padding: 20px;
            }

            h1 {
                font-size: 1.8em;
            }

            .question-block {
                padding: 15px;
            }

            .options label {
                padding: 8px;
                font-size: 0.95em;
            }

            button {
                padding: 10px 20px;
                font-size: 0.9em;
            }
        }

        @media (max-width: 480px) {
            .container {
                padding: 15px;
                border-radius: 10px;
            }

            h1 {
                font-size: 1.5em;
                margin-bottom: 20px;
            }

            .question-block {
                padding: 10px;
                border-radius: 10px;
            }

            .question-text {
                font-size: 1em;
                margin-bottom: 10px;
            }

            .options label {
                padding: 7px;
                font-size: 0.9em;
                margin-bottom: 8px;
            }

            .options input[type="radio"] {
                transform: scale(0.9); /* Slightly smaller radio buttons */
            }

            button {
                padding: 8px 15px;
                font-size: 0.85em;
                border-radius: 8px;
            }

            .score-container {
                padding: 15px;
                border-radius: 10px;
            }

            .score-container h2 {
                font-size: 1.2em;
                margin-bottom: 15px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>IMK Quiz</h1>
        <div id="quiz-container"></div>
        <button id="submit-btn">Submit Answers</button>
        <div id="score-container" class="score-container" style="display: none;">
            <h2>Your Score: <span id="score">0</span> / 50</h2>
            <button id="restart-btn">Try Again</button>
        </div>
    </div>
    <script>
        const questionsData = [
            { question: "Prinsip dasar suatu sistem komputer adalah ....", options: ["input dan proses", "proses dan output", "input dan output", "input, proses, output"], answer: "input, proses, output" },
            { question: "Interaksi antara pengguna dan komputer dapat terjadi jika tersedia ....", options: ["pengguna", "komputer", "programmer", "media"], answer: "media" },
            { question: "User-friendly digunakan untuk merujuk pada karakter yang dimiliki oleh ....", options: ["program aplikasi", "program kerja", "pengguna", "programmer"], answer: "program aplikasi" },
            { question: "Interaksi antara pengguna dan komputer dapat terjadi ketika pengguna ....", options: ["menyalakan komputer", "menggunakan mouse", "menyentuh keyboard", "mengetikkan sesuatu"], answer: "mengetikkan sesuatu" },
            { question: "Fokus interaksi manusia dan komputer ditinjau dari perspektif ilmu komputer adalah interaksi antara ....", options: ["manusia dengan manusia", "manusia dengan pengguna", "mesin dengan komputer", "manusia dengan komputer"], answer: "manusia dengan komputer" },
            { question: "Seorang perancang antarmuka harus mempertimbangkan kenyamanan pengguna, oleh sebab itu dia membutuhkan pengetahuan dari bidang ilmu lain, yaitu ....", options: ["Antropologi", "Sosiologi", "Psikologi", "Ergonomi"], answer: "Psikologi" },
            { question: "Seorang perancang antarmuka juga harus dapat memahami sifat dan kebiasaan pengguna. Pengetahuan ini dapat diperoleh dari bidang ilmu ....", options: ["Psikologi", "Ergonomi", "Perancangan Grafis dan Tipografi", "Perancangan Industri"], answer: "Psikologi" },
            { question: "Antarmuka suatu sistem yang dilengkapi dengan gambar atau ilustrasi yang dapat mempermudah pengguna dapat dikembangkan dengan mempelajari ilmu ....", options: ["Psikologi", "Ergonomi", "Perancangan Grafis dan Tipografi", "Perancangan Industri"], answer: "Perancangan Grafis dan Tipografi" },
            { question: "Melalui antarmuka pengguna berdialog dengan komputer. Dialog dapat terjadi jika ada sarana komunikasi yang memadai. Hal ini dapat diperoleh dengan mempelajari ilmu ....", options: ["Psikologi", "Linguistik", "Ilmu Komputer", "Teknik Elektronika"], answer: "Linguistik" },
            { question: "Perancangan antarmuka suatu sistem tidak dapat dilepaskan dari perangkat keras, oleh sebab itu diperlukan pengetahuan bidang ilmu ....", options: ["Psikologi", "Linguistik", "Ilmu Komputer", "Teknik Elektronika"], answer: "Teknik Elektronika" },
            { question: "Salah satu kriteria yang harus dimiliki oleh sebuah perangkat lunak adalah \"ramah dengan pengguna”, biasa disebut ....", options: ["user-friendly", "user-ability", "user-interface", "user-center design"], answer: "user-friendly" },
            { question: "Pengembangan fasilitas antarmuka, selain harus menangani sejumlah peranti kontrol, juga harus memperhatikan selera dan kebiasaan pengguna yang ....", options: ["homogen", "heterogen", "monoton", "seragam"], answer: "heterogen" },
            { question: "Proses perancangan dan pengembangan antarmuka memerlukan peranti ....", options: ["masukan", "keluaran", "bantu", "modern"], answer: "bantu" },
            { question: "Dalam pengembangan antarmuka lebih baik terlebih dahulu dikembangkan ....", options: ["contohnya", "prototipenya", "bentuknya", "modelnya"], answer: "prototipenya" },
            { question: "Antarmuka yang konsisten dapat dikembangkan untuk sejumlah aplikasi dengan memanfaatkan ....", options: ["program bantu yang sama", "program bantu yang berbeda", "prototipe yang sama", "model yang sama"], answer: "program bantu yang sama" },
            { question: "Sebuah program aplikasi terdiri dari dua bagian penting, yaitu ....", options: ["antarmuka dan aplikasi", "prototipe dan antarmuka", "prototipe dan aplikasi", "program dan aplikasi"], answer: "antarmuka dan aplikasi" },
            { question: "Antarmuka berfungsi sebagai sarana dialog antara ....", options: ["manusia dengan pengguna", "manusia dengan komputer", "komputer dengan mesin", "komputer dengan program"], answer: "manusia dengan komputer" },
            { question: "Bagian antarmuka lebih banyak berurusan dengan cara .....", options: ["penyajian informasi", "penggunaan gadget", "penyelesaian masalah", "pembuatan program"], answer: "penyajian informasi" },
            { question: "Pada antarmuka tidak boleh ada keterlambatan antara tindakan pengguna dan sistem, karena hal ini akan menyebabkan pengguna .....", options: ["senang", "sabar", "frustrasi", "acuh"], answer: "frustrasi" },
            { question: "Berikut adalah keuntungan menggunakan peranti bantu untuk pengembangan antarmuka, kecuali program antarmuka .....", options: ["modular", "reusable", "easy to modify", "rigid"], answer: "rigid" },
            { question: "Seorang perancang sistem perlu memahami cara manusia mengolah informasi, hal ini termasuk dalam aspek .....", options: ["middleware", "software", "hardware", "brainware"], answer: "brainware" },
            { question: "Manusia dan komputer memiliki beberapa persamaan, antara lain mempunyai otak. Otak pada komputer adalah .....", options: ["Central Processing Unit", "motherboard", "hard drive", "Random Access Memory"], answer: "Central Processing Unit" },
            { question: "Manusia hanya mampu fokus terhadap satu pekerjaan dalam satu waktu, sedangkan komputer dapat melakukan beberapa pekerjaan dalam satu waktu yang disebut .....", options: ["multiprogramming", "multitasking", "multithreading", "multiprocessing"], answer: "multitasking" },
            { question: "Suatu tindakan yang jarang dilakukan akan diolah dalam diri manusia secara .....", options: ["sadar", "tidak sadar", "otomatis", "spontan"], answer: "sadar" },
            { question: "Suatu tindakan baru dapat diolah dalam diri manusia secara otomatis melalui .....", options: ["tindakan", "latihan", "gambar", "suara"], answer: "latihan" },
            { question: "Pengolahan yang melibatkan organ-organ sensori ke otak disebut pengolahan .....", options: ["motorik", "kognitif", "perseptual", "konseptual"], answer: "perseptual" },
            { question: "Urutan langkah pengolahan informasi adalah .....", options: ["1-2-3-4", "2-1-3-4", "3-4-1-2", "4-3-2-1"], answer: "2-1-3-4" },
            { question: "Register sensori penglihatan menerima informasi dari luar dan akan memegang informasi selama .....", options: ["0,2 detik", "2 detik", "0,2 menit", "2 menit"], answer: "0,2 detik" },
            { question: "Short-Term Memory memiliki kapasitas terbatas, oleh sebab itu jika diberikan suatu nomor telepon 0217505295, maka akan lebih mudah mengingatnya jika nomor tersebut dibagi menjadi beberapa kelompok, seperti 021 750 5295. Teknik ini disebut .....", options: ["chopping", "cutting", "chunking", "grouping"], answer: "chunking" },
            { question: "Kemampuan motor skills seperti mengendarai sepeda termasuk dalam .....", options: ["sensory memory", "short-term memory", "long-term memory", "explicit memory"], answer: "long-term memory" },
            { question: "Banyaknya cahaya yang dipantulkan oleh permukaan obyek disebut .....", options: ["luminous", "illumination", "luminance", "luminescent"], answer: "luminance" },
            { question: "Semakin besar luminansi dari sebuah obyek, menyebabkan diameter bola mata mengecil karena .....", options: ["meningkatkan fokus", "silau", "buram", "terlalu terang"], answer: "silau" },
            { question: "Hubungan antara cahaya yang dipancarkan oleh suatu obyek dan cahaya dari latar belakang obyek tersebut disebut .....", options: ["luminansi", "kontras", "kecerahan", "medan penglihatan"], answer: "kontras" },
            { question: "Sudut yang dibentuk ketika mata bergerak ke kiri terjauh dan ke kanan terjauh dapat dibagi menjadi .....", options: ["1 daerah", "2 daerah", "3 daerah", "4 daerah"], answer: "3 daerah" },
            { question: "Ketika kepala dan mata dalam keadaan diam, daerah penglihatan monokuler mempunyai rentang antara .....", options: ["0” sampai 60”", "62” sampai 70”", "94\" sampai 104”", "100” sampai 166”"], answer: "94\" sampai 104”" },
            { question: "Mata dapat membedakan warna secara akurat ketika posisi obyek terhadap mata membentuk sudut sebesar .....", options: ["15°", "30°", "45°", "60°"], answer: "30°" },
            { question: "Efek chromostereopsis seringkali timbul pada kombinasi warna .....", options: ["merah dan biru", "biru dan kuning", "kuning dan hijau", "hijau dan biru"], answer: "merah dan biru" },
            { question: "Kombinasi warna yang baik adalah .....", options: ["merah, biru, hijau", "magenta, hijau, merah", "merah, kuning, putih", "magenta, biru, hijau"], answer: "magenta, biru, hijau" },
            { question: "Warna dingin biasanya digunakan untuk menunjukkan status atau informasi latar belakang. Warna dingin antara lain adalah .....", options: ["biru", "merah", "oranye", "kuning"], answer: "biru" },
            { question: "Merah, kuning, biru termasuk warna .....", options: ["primer", "sekunder", "tersier", "netral"], answer: "primer" },
            { question: "Kejadian yang diinginkan oleh pengguna dalam struktur tindakan disebut .....", options: ["goal", "eksekusi", "dunia nyata", "evaluasi"], answer: "goal" },
            { question: "Satu langkah tindakan pada fase eksekusi adalah .....", options: ["memahami status dunia nyata", "membentuk keinginan", "menginterpretasikan persepsi", "mengevaluasi hasil interpretasi"], answer: "membentuk keinginan" },
            { question: "Satu langkah tindakan pada fase evaluasi hasil interpretasi adalah.....", options: ["memahami status dunia nyata", "menentukan goal", "membentuk keinginan", "menentukan urutan tindakan yang akan dilakukan"], answer: "menentukan urutan tindakan yang akan dilakukan" },
            { question: "Gulf of execution adalah jarak pemisah eksekusi antara .....", options: ["pengguna dan sistem", "pengguna dan pengembang", "pengembang dan sistem", "pengembang dan programmer"], answer: "pengguna dan sistem" },
            { question: "Kerangka Kerja Interaksi SPMK terdiri dari .....", options: ["satu fase", "dua fase", "tiga fase", "empat fase"], answer: "empat fase" },
            { question: "Ketika bahasa masukan diterjemahkan ke dalam bahasa mesin merupakan langkah dalam fase .....", options: ["eksekusi", "evaluasi", "artikulasi", "observasi"], answer: "eksekusi" },
            { question: "Saat pengguna mengartikan hasil yang muncul di layar dan mencocokkannya dengan kejadian yang diinginkannya, masuk dalam fase .....", options: ["eksekusi", "evaluasi", "artikulasi", "observasi"], answer: "evaluasi" },
            { question: "Sistem menunjukkan perubahan statusnya dalam bahasa keluaran merupakan langkah dalam eksekusi, yaitu .....", options: ["artikulasi", "pengerjaan", "penyajian", "pengamatan"], answer: "penyajian" },
            { question: "Ketika sistem menggunakan data yang diperoleh dari bahasa masukan untuk melakukan suatu operasi, hal ini masuk dalam langkah .....", options: ["artikulasi", "pengerjaan", "penyajian", "pengamatan"], answer: "pengerjaan" },
            { question: "Proses yang ditunjukkan dengan adanya indikator yang bergerak atau ikon berbentuk jam, muncul saat fase .....", options: ["eksekusi", "evaluasi", "artikulasi", "observasi"], answer: "eksekusi" },
            { question: "Model yang diciptakan oleh pengguna ketika pengguna berinteraksi dengan suatu sistem adalah model .....", options: ["kognitif", "perseptual", "mental", "perancang"], answer: "mental" },
            { question: "Model mental merupakan representasi pribadi dari suatu objek, ide, atau proses, yang dihasilkan oleh seseorang selama berlangsung proses .....", options: ["kognitif", "afektif", "motorik", "psikomotorik"], answer: "kognitif" },
            { question: "Kemampuan pengguna memformulasikan kerangka kerja suatu sistem bergantung pada .....", options: ["pendidikan", "sosial ekonomi", "pengalaman", "umur"], answer: "pengalaman" },
            { question: "Apabila model mental pengguna cukup dekat dengan cara bekerjanya suatu sistem, maka pengguna akan .....", options: ["kebingungan menggunakan sistem tersebut", "ketakutan menggunakan sistem tersebut", "merasa senang menggunakan sistem tersebut", "kesulitan menggunakan sistem tersebut"], answer: "merasa senang menggunakan sistem tersebut" },
            { question: "Model mental bersifat .....", options: ["ilmiah", "konsisten", "stabil", "parsial"], answer: "parsial" },
            { question: "Perancang antarmuka harus memiliki pemahaman tentang berbagai model mental pengguna. Model mental pengguna paling efektif dapat diperoleh melalui .....", options: ["wawancara dengan pengguna", "pengamatan pada pengguna", "penelitian melibatkan pengguna", "data pengguna"], answer: "penelitian melibatkan pengguna" },
            { question: "Jarak semantik antara pengguna dengan sistem adalah jarak antara .....", options: ["penampakan fisik suatu peranti dengan fungsi yang sesungguhnya", "fungsionalitas suatu peranti dengan yang sesungguhnya diinginkan pengguna", "penampakan fisik suatu peranti dengan yang sesungguhnya diinginkan pengguna", "fungsionalitas suatu peranti dengan fungsi yang sesungguhnya"], answer: "fungsionalitas suatu peranti dengan yang sesungguhnya diinginkan pengguna" },
            { question: "Jarak artikulatori adalah jarak antara .....", options: ["penampakan fisik suatu peranti dengan fungsi yang sesungguhnya", "fungsionalitas suatu peranti dengan yang sesungguhnya diinginkan pengguna", "penampakan fisik suatu peranti dengan yang sesungguhnya diinginkan pengguna", "fungsionalitas suatu peranti dengan fungsi yang sesungguhnya"], answer: "penampakan fisik suatu peranti dengan yang sesungguhnya diinginkan pengguna" },
            { question: "Semakin rendah tingkat affordance suatu perangkat, semakin .....", options: ["cepat mempelajarinya", "banyak penggunanya", "sulit merancangnya", "sulit menggunakannya"], answer: "sulit menggunakannya" },
            { question: "Contoh perancangan perangkat yang memiliki affordance rendah adalah pintu dengan .....", options: ["sensor", "knop", "pelat besi", "hendel"], answer: "pelat besi" },
            { question: "Antarmuka berpusat-pada-implementasi lebih disukai oleh kalangan .....", options: ["awam", "pemula", "praktis", "teknis"], answer: "teknis" },
            { question: "Perancangan antarmuka berpusat-pada-implementasi berfokus pada .....", options: ["tahap implementasi", "proses implementasi", "model implementasi", "waktu implementasi"], answer: "tahap implementasi" },
            { question: "Paradigma perancangan konseptual dan visual suatu antarmuka yang didasarkan pada intuisi bagaimana sesuatu bekerja adalah .....", options: ["implementation-centric", "metaphoric", "idiomatic", "affordance"], answer: "metaphoric" },
            { question: "Paradigma perancangan konseptual dan visual suatu antarmuka yang didasarkan pada proses manusiawi yang alami adalah .....", options: ["implementation-centric", "metaphoric", "idiomatic", "affordance"], answer: "affordance" },
            { question: "Ketika kita bekerja menggunakan Microsoft Word, kita dapati gambar gunting pada antarmukanya. Penggunaan gambar gunting merupakan penerapan paradigma .....", options: ["implementation-centric", "metaphoric", "idiomatic", "affordance"], answer: "metaphoric" },
            { question: "Ketika Anda melihat ikon keranjang sampah, Anda langsung tahu cara menggunakannya, karena pernah mempelajari cara kerja keranjang sampah yang sebenarnya, hal ini merupakan penerapan paradigma .....", options: ["implementation-centric", "metaphoric", "idiomatic", "affordance"], answer: "metaphoric" },
            { question: "Paradigma idiomatik berfokus pada .....", options: ["pengetahuan teknis", "intuisi fungsi", "pembelajaran", "koneksi asosiatif"], answer: "pembelajaran" },
            { question: "Elemen-elemen GUI (graphical user interface) yang merupakan metafora adalah .....", options: ["hyperlinks", "windows", "nested folders", "desktops"], answer: "desktops" },
            { question: "Simbol keranjang (shopping cart) yang dapat kita temui pada antarmuka web toko online digunakan untuk membawa barang merupakan metafora .....", options: ["visual", "fungsional", "organisasional", "global"], answer: "fungsional" },
            { question: "Tanda seru pada gambar di bawah ini merupakan penerapan .....", options: ["iconic metaphor", "indexical metaphor", "contextual metaphor", "hybrid metaphor"], answer: "indexical metaphor" },
            { question: "Salah satu kesalahan umum yang sering dilakukan oleh perancang sistem adalah .....", options: ["eksperimen yang teranalisis", "tradisi yang kekinian", "penundaan evaluasi \"sampai waktu luang”", "evaluasi formal yang menggunakan kelompok subjek yang sesuai"], answer: "penundaan evaluasi \"sampai waktu luang”" },
            { question: "Salah satu jenis fitur tampilan yang dapat menangkap kesan subjektif pengguna adalah .....", options: ["karakter", "konsekuensi", "komunikasi", "kuantisasi"], answer: "karakter" },
            { question: "Salah satu aturan dalam kepuasan berinteraksi adalah .....", options: ["status sistem", "instruksi", "kecepatan", "konsistensi"], answer: "konsistensi" },
            { question: "Seiring dengan frekuensi pengguna yang meningkat, pengguna berkeinginan untuk mengurangi jumlah interaksi dan meningkatkan kecepatan berinteraksi. Hal tersebut dikenal dengan istilah .....", options: ["umpan balik", "fasilitas kunci-cepat", "pencegahan kesalahan", "rancangan dialog"], answer: "fasilitas kunci-cepat" },
            { question: "Penyajian secara visual pada kepuasan berinteraksi, dapat digunakan untuk menunjukkan suatu perubahan yang bersifat eksplisit. Kepuasan berinteraksi tersebut, termasuk ke dalam aturan .....", options: ["konsistensi", "dukungan pada locus of control internal", "pencegahan dan penanganan kesalahan", "umpan balik yang inovatif"], answer: "umpan balik yang inovatif" },
            { question: "Suatu rancangan dialog yang mengarah pada penutupan (closure), dibagi ke dalam tiga kelompok bagian yaitu .....", options: ["awal, tengah, dan akhir", "depan, tengah, dan belakang", "maju, stabil, dan mundur", "atas, tengah, dan bawah"], answer: "awal, tengah, dan akhir" },
            { question: "Suatu sistem memiliki kemampuan untuk mendeteksi kesalahan, dengan memberikan instruksi yang sederhana, spesifik, dan konstruktif untuk melakukan pemulihan. Kemampuan tersebut dikenal dengan .....", options: ["penetapan kesalahan dan penanganan kesalahan", "penetapan kesalahan dan pemulihan kesalahan", "pencegahan kesalahan dan penanganan kesalahan", "pencegahan kesalahan dan pemulihan kesalahan"], answer: "pencegahan kesalahan dan penanganan kesalahan" },
            { question: "Fitur kepuasan berinteraksi yang dapat mengurangi kecemasan pengguna, karena pengguna mengetahui bahwa kesalahan yang mungkin mereka perbuat dapat dibatalkan, fitur tersebut adalah .....", options: ["pengetahuan tindakan yang mudah", "pembalikan tindakan yang mudah", "pengetahuan tingkatan yang mudah", "pembalikan tingkatan yang mudah"], answer: "pembalikan tindakan yang mudah" },
            { question: "Saat pengguna berasumsi bahwa sistem akan memberikan tanggapan yang sesuai dengan tindakan pengguna, maka aturan kepuasan berinteraksi harus memiliki aturan yang mendukung pada .....", options: ["locus of control intercept", "locus of control external", "locus of control interactive", "locus of control internal"], answer: "locus of control internal" },
            { question: "Keterbatasan manusia untuk mengolah informasi pada memori jangka pendek, mensyaratkan bahwa tampilan suatu sistem harus .....", options: ["kompleks", "rumit", "sederhana", "kekurangan"], answer: "sederhana" },
            { question: "Sebuah sistem yang mampu memotivasi penggunanya untuk menggunakannya, menarik, menyenangkan, dan lain-lain, disebut dengan .....", options: ["using", "useful", "used", "usable"], answer: "usable" },
            { question: "Jika sistem mudah dipelajari dan digunakan maka termasuk ke dalam salah satu komponen kualitas untuk menentukan kebergunaan sebuah sistem, yaitu .....", options: ["efficiency", "satisfaction", "memorability", "learnability"], answer: "learnability" },
            { question: "Untuk memberi kemudahan pada pengguna yang jarang menggunakan sistem, sistem harus memiliki kemampuan untuk .....", options: ["errors", "memorability", "efficiency", "learnability"], answer: "memorability" },
            { question: "Suatu cara yang dilakukan sistem untuk mendukung pengguna dalam melakukan pekerjaannya, disebut dengan .....", options: ["efficiency", "memorability", "learnability", "satisfaction"], answer: "efficiency" },
            { question: "Proses untuk mengukur karakteristik interaksi manusia dan komputer dari sebuah sistem, dan mengidentifikasi kelemahannya, sehingga perancang sistem dapat memperbaikinya dengan cepat, disebut dengan uji .....", options: ["kualitas", "tampilan", "keefektifan", "kebergunaan"], answer: "kebergunaan" },
            { question: "Menurut Levi dan Conrad (1997), uji kebergunaan dibagi menjadi tiga jenis, yaitu .....", options: ["uji eksploratori, uji threshold, dan uji perbandingan", "uji eksploratori, uji threshold, dan uji perbaikan", "uji eksploitasi, uji threshold, dan uji perbandingan", "uji eksploitasi, uji threshold, dan uji perbaikan"], answer: "uji eksploratori, uji threshold, dan uji perbandingan" },
            { question: "Sebuah pengujian untuk memberikan penilaian terhadap produk jadi, untuk mengukur peningkatan yang telah dilakukan terhadap produk sebelumnya, atau untuk membandingkannya dengan produk sejenis dari perusahaan lain adalah uji .....", options: ["formal", "formatif", "normatif", "sumatif"], answer: "sumatif" },
            { question: "Tujuan metode pemilihan kartu dalam uji kebergunaan adalah mengelompokkan informasi dalam jumlah .....", options: ["besar menjadi bagian-bagian yang lebih kecil dan dapat dikelola dengan sukar", "kecil menjadi bagian-bagian yang lebih besar dan dapat dikelola dengan mudah", "kecil menjadi bagian-bagian yang lebih kecil yang dapat dikelola dengan sukar", "besar menjadi bagian-bagian yang lebih kecil yang dapat dikelola dengan lebih mudah"], answer: "besar menjadi bagian-bagian yang lebih kecil yang dapat dikelola dengan lebih mudah" },
            { question: "Uji kebergunaan yang melibatkan ahli AMK (Analisis Multi Kriteria) adalah evaluasi .....", options: ["heuristik", "kartu", "semantik", "skenario"], answer: "heuristik" },
            { question: "Pengguna akhir (end user) diberi kesempatan untuk menguji sistem menggunakan tugas tertentu yang sudah dirancang. Uji kebergunaan ini disebut .....", options: ["uji berbasis skenario", "evaluasi heuristik", "pemilihan kartu", "evaluasi kuantitatif"], answer: "uji berbasis skenario" },
            { question: "Salah satu dari tiga elemen manipulasi langsung adalah .....", options: ["penyajian visual dari obyek yang tidak akan dimanipulasi", "tindakan fisik sebagai pengganti teks masukan", "penyampaian audio yang tidak dimanipulasi", "reaksi langsung yang tidak dapat dilihat"], answer: "tindakan fisik sebagai pengganti teks masukan" },
            { question: "Penggantian perintah yang diketik dengan tindakan menunjuk ke obyek yang diinginkan adalah .....", options: ["ide utama dari manipulasi langsung", "jenis dari manipulasi langsung", "rangkaian kelompok dari manipulasi langsung", "karakteristik dari manipulasi langsung"], answer: "ide utama dari manipulasi langsung" },
            { question: "Dua aspek penting pada manipulasi langsung adalah jarak dan .....", options: ["keterbukaan", "keleluasaan", "keterlibatan", "keterbatasan"], answer: "keterlibatan" },
            { question: "Manipulasi program adalah .....", options: ["cara pengguna mengelola data dalam aplikasi tertentu", "tindakan pengguna yang menghasilkan umpan balik", "tindakan pengguna yang menghasilkan output program", "cara pengguna menggunakan program aplikasi untuk menyelesaikan suatu tugas"], answer: "cara pengguna menggunakan program aplikasi untuk menyelesaikan suatu tugas" },
            { question: "Contoh aplikasi manipulasi isi adalah .....", options: ["Microsoft Word", "Adobe Photoshop", "PDF Reader", "Mathtype"], answer: "Microsoft Word" },
            { question: "Tindakan bertahap pada antarmuka dengan umpan balik segera untuk semua tindakan yang diambil, merupakan salah satu fitur dari antarmuka .....", options: ["manipulasi langsung", "manipulasi isi", "manipulasi tidak langsung", "manipulasi program"], answer: "manipulasi langsung" },
            { question: "Fase sebelum pengguna melakukan suatu tindakan, di mana pada fase ini tidak ada sesuatu yang terjadi, merupakan fase .....", options: ["penghentian", "aktivasi", "evaluasi", "bebas"], answer: "bebas" },
            { question: "Pengolah kata modern yang memberikan kemudahan kepada pengguna untuk mendapatkan hasil cetakan seperti apa yang muncul pada layar tampilan disebut .....", options: ["editor teks", "kontrol proses", "simulator", "kontrol lalu lintas"], answer: "editor teks" },
            { question: "Salah satu keuntungan dari manipulasi langsung adalah .....", options: ["memerlukan program yang rumit", "sulit untuk dioperasikan", "mengurangi waktu pembelajaran", "menampilkan visual yang tidak diinginkan"], answer: "mengurangi waktu pembelajaran" },
            { question: "Salah satu kerugian dari manipulasi langsung adalah .....", options: ["mempunyai analogi yang jelas", "memerlukan tampilan grafis berkinerja tinggi", "memerlukan program yang ringan", "memerlukan perancangan tampilan tidak bersyarat"], answer: "memerlukan tampilan grafis berkinerja tinggi" },
            { question: "Kata lain dari peranti penunjuk mouse adalah .....", options: ["tetikus", "tombol", "tikus", "tetombol"], answer: "tetikus" },
            { question: "Jumlah tombol mouse yang dikeluarkan oleh perusahaan Macintosh adalah .....", options: ["empat", "tiga", "dua", "satu"], answer: "satu" },
            { question: "Jumlah tombol mouse yang dikeluarkan oleh perusahaan Borland adalah .....", options: ["satu", "dua", "tiga", "empat"], answer: "tiga" },
            { question: "Tombol pada mouse yang selalu digunakan untuk melakukan fungsi manipulasi langsung seperti mengaktifkan, memilih, menggambar, dan lain-lain, adalah tombol .....", options: ["kanan", "atas", "kiri", "tengah"], answer: "kiri" },
            { question: "Tombol pada mouse yang dimanfaatkan untuk tombol singkat adalah tombol .....", options: ["kiri", "tengah", "atas", "kanan"], answer: "kanan" },
            { question: "Tombol pada mouse yang memungkinkan akses langsung ke properti dan tindakan berdasar konteks pada obyek dan fungsi adalah tombol .....", options: ["kanan", "atas", "kiri", "atas"], answer: "kanan" },
            { question: "Proses yang dilakukan pengguna untuk menggerakkan mouse sampai kursor mouse-nya berada di atas obyek yang dimaksud, disebut dengan operasi .....", options: ["meng-klik", "meng-klik dan menggeser", "menunjuk", "menunjuk dan menggeser"], answer: "menunjuk" },
            { question: "Operasi mouse untuk memilih, mengubah bentuk, mengubah posisi, menggambar, dan menggeser dan menjatuhkan, disebut dengan operasi meng-klik dan .....", options: ["menunjuk", "menggeser", "meng-klik ganda", "menggeser ganda"], answer: "menggeser" },
            { question: "Operasi memegang mouse dalam keadaan diam, dan meng-klik salah satu tombol mouse kemudian melepasnya, disebut dengan operasi .....", options: ["menunjuk", "menggeser", "mengganda", "meng-klik"], answer: "meng-klik" },
            { question: "Suatu proses meng-klik tunggal diteruskan dengan suatu tindakan lain, disebut dengan operasi .....", options: ["meng-klik", "meng-klik tunggal", "meng-klik ganda", "meng-klik tak beraturan"], answer: "meng-klik ganda" },
            { question: "Pengorganisasian tugas adalah salah satu faktor yang perlu diperhatikan dalam .....", options: ["implementasi sistem", "aplikasi sistem", "perancangan sistem", "realisasi sistem"], answer: "perancangan sistem" },
            { question: "Gambar berikut menunjukkan skema jenis menu .....", options: ["linier", "biner", "jaring berputar", "jaring tak berputar"], answer: "linier" },
            { question: "Gambar berikut adalah contoh jenis menu .....", options: ["biner", "tunggal dengan banyak pilihan", "gulung", "tarik"], answer: "tarik" },
            { question: "Ragam menu yang menuliskan pilihan-pilihan dengan menampilkan menu dalam keseluruhan layar, disebut dengan .....", options: ["gulung", "datar", "kotak kombo", "penggeser"], answer: "datar" },
            { question: "Menu yang menampilkan sejumlah pilihan sesuai dengan ukuran daerah kerja layar tampilan yang dapat digunakan, disebut dengan menu .....", options: ["tarik", "datar", "gulung", "biner"], answer: "gulung" },
            { question: "Gambar berikut merupakan contoh penerapan menu .....", options: ["penggeser", "gulung", "kotak kombo", "tarik"], answer: "kotak kombo" },
            { question: "Jenis menu yang memungkinkan pengguna untuk melihat pilihan sesuai konteksnya dan menghindari adanya pilihan lain yang menganggu dan menghabiskan kapling pada layar tampilan adalah .....", options: ["breadcrumb", "sambungan tertanam", "tarik", "struktur pohon"], answer: "tarik" },
            { question: "Menu yang menampilkan semua pilihan, hanya saja pilihan-pilihan yang terletak jauh dari posisi kursor/penyorot akan ditampilkan dengan menggunakan font atau ikon berukuran kecil, sementara pilihan yang dekat dengan posisi kursor/penyorot akan ditampilkan menggunakan font atau ikon berukuran normal adalah .....", options: ["mata ikan", "datar", "berstruktur pohon", "tarik"], answer: "mata ikan" },
            { question: "Ketika jumlah pilihan semakin besar sehingga menjadi lebih sukar untuk diakomodasi, perancang dapat mengelompokkan pilihan-pilihan tersebut berdasarkan kriteria tertentu. Jenis menu tersebut adalah menu .....", options: ["tarik", "datar", "mata ikan", "berstruktur pohon"], answer: "berstruktur pohon" },
            { question: "Pengguna akan semakin mengalami kesulitan untuk menentukan posisinya ketika kedalaman menu bertambah. Situasi ini sering disebut dengan .....", options: ["konsistensi", "disorientasi", "modernisasi", "validasi"], answer: "disorientasi" },
            { question: "Salah satu pengelompokan pilihan dalam menu struktur pohon adalah .....", options: ["pisahkan pilihan-pilihan yang secara logis serupa", "pisahkan pilihan-pilihan yang secara logis berbeda", "satukan pilihan-pilihan yang secara logis serupa", "satukan pilihan-pilihan yang secara logis berbeda"], answer: "pisahkan pilihan-pilihan yang secara logis serupa" },
            { question: "Salah satu urutan penyajian menu yang tepat adalah berdasarkan .....", options: ["acak", "tak terhingga", "sifat non-fisik", "sifat fisik"], answer: "sifat fisik" },
            { question: "Salah satu pemilihan ungkapan yang tepat yaitu menggunakan terminologi yang .....", options: ["sudah dikenal dan konsisten", "sudah dikenal dan tidak konsisten", "tidak dikenal dan konsisten", "tidak dikenal dan tidak konsisten"], answer: "sudah dikenal dan konsisten" },
            { question: "Studi yang dilakukan oleh Teitelbaum dan Granda (1983) mengenai judul menu menunjukkan bahwa pengguna memerlukan waktu .....", options: ["satu kali lebih lama untuk memilih menu yang sama ketika posisi menunya berpindah-pindah dibandingkan jika posisi menunya tetap", "dua kali lebih lama untuk memilih menu yang sama ketika posisi menunya berpindah-pindah dibandingkan jika posisi menunya tetap", "dua kali lebih lama untuk memilih menu yang sama ketika posisi menunya berpindah-pindah dibandingkan jika posisi menunya tidak tetap", "satu kali lebih lama untuk memilih menu yang sama ketika posisi menunya berpindah-pindah dibandingkan jika posisi menunya tidak tetap"], answer: "dua kali lebih lama untuk memilih menu yang sama ketika posisi menunya berpindah-pindah dibandingkan jika posisi menunya tetap" },
            { question: "Penulisan menu judul rapi kiri, menandakan bahwa perancang menu konsisten pada komponen menu .....", options: ["petunjuk", "laporan status", "penulisan judul", "pesan kesalahan"], answer: "penulisan judul" },
            { question: "Pilihan menu yang ditulis rapi kiri, dengan nomor atau huruf tertentu yang mendahului judul pilihan secara lengkap. Baris kosong seringkali digunakan untuk memisahkan kelompok pilihan tertentu. Jika digunakan banyak kolom, penomoran atau penggunaan huruf harus tetap konsisten. Hal tersebut merupakan salah satu komponen menu .....", options: ["laporan status", "penulisan judul", "penempatan pilihan", "petunjuk"], answer: "penempatan pilihan" },
            { question: "Jika pengguna memilih pilihan yang tidak dapat diterima, maka harus disediakan komponen menu .....", options: ["penulisan judul", "pesan kesalahan", "penempatan pilihan", "petunjuk"], answer: "pesan kesalahan" },
            { question: "Sejumlah sistem mempunyai semacam tanda yang menunjukkan dari menu yang sedang dikunjungi, halaman yang sedang dilihat, atau pilihan yang harus dipilih untuk menyelesaikan suatu tugas. Tanda tersebut merupakan komponen menu .....", options: ["laporan status", "petunjuk", "penulisan judul", "pesan kesalahan"], answer: "laporan status" },
            { question: "Urutan menu nama anggota berikut disusun berdasarkan .....", options: ["numerik", "jarak", "waktu", "alfabetis"], answer: "alfabetis" },
            { question: "Berikut terdapat menu yang terdiri atas: A. Sekolah Lanjutan Tingkat Atas B. Alamat C. Sekolah Lanjutan Tingkat Pertama D. Nama E. Data Pendidikan F. Tempat Tanggal Lahir G. Data Pribadi H. Sekolah Dasar Pengelompokan menu yang paling dapat diterima dan dimengerti oleh pengguna adalah .....", options: ["Data Pribadi, Data Pendidikan", "Data Pendidikan, Data Pribadi", "Nama, Alamat, Tempat Tanggal Lahir", "Sekolah Dasar, Sekolah Lanjutan Tingkat Pertama, Sekolah Lanjutan Tingkat Atas"], answer: "Data Pribadi, Data Pendidikan" },
            { question: "Perintah DOS yang berfungsi untuk menampilkan nama-nama berkas yang tersimpan di dalam hard disk D adalah .....", options: ["C:\\DIR", "D:/sDIR", "D:\\DIR", "C::DIR"], answer: "D:\\DIR" },
            { question: "Perintah UNIX yang berfungsi untuk mencetak suatu berkas ke printer yang terhubung dengan dengan sistem UNIX adalah .....", options: ["ls", "lps", "lpr", "vi"], answer: "lpr" },
            { question: "Berikut ini merupakan perintah DOS untuk menyalin berkas C:\\COPY \"*.png ANASKAH. Dari perintah tersebut, jenis berkas yang akan disalin adalah .....", options: ["dokumen", "gambar", "video", "suara"], answer: "gambar" },
            { question: "Di bawah ini yang merupakan perintah luar pada DOS adalah .....", options: ["C:\\DOS\\FORMAT A: /S", "C:\\COPY \".DOC ANASKAH", "C:\\DIR \".BAT /S", "C:\\DIR"], answer: "C:\\DOS\\FORMAT A: /S" },
            { question: "Perintah yang digunakan untuk menampilkan nama-nama berkas pada UNIX adalah .....", options: ["dir", "ls", "vi", "who"], answer: "ls" },
            { question: "Keuntungan dari penggunaan dialog berbasis perintah tunggal adalah .....", options: ["memerlukan pelatihan yang lama", "membutuhkan penggunaan yang teratur", "appealing", "jelek menangani kesalahan"], answer: "membutuhkan penggunaan yang teratur" },
            { question: "Perbedaan mendasar dari perintah tunggal pada DOS dan UNIX adalah .....", options: ["UNIX tidak alamiah", "UNIX lebih mudah diingat", "DOS lebih alamiah", "DOS lebih lengkap"], answer: "UNIX lebih mudah diingat" },
            { question: "Dialog berbasis bahasa pemrograman merupakan ragam dialog yang memungkinkan pengguna untuk mengemas sejumlah perintah ke dalam suatu bentuk berkas yang sering disebut dengan .....", options: ["source code", "batch file", "execution file", "path file"], answer: "batch file" },
            { question: "Berikut ini yang merupakan contoh instruksi bahasa alami adalah .....", options: ["Tampilkan semua mahasiswa yang meregistrasi matakuliah - IMK", "Tampilkan semua mahasiswa yang mempunyai nilai IMK - “A\"", "Hapus semua mahasiswa yang meregistrasi matakuliah Jaringan Komputer", "Tampilkan semua mahasiswa yang mempunyai IPK - 3"], answer: "Tampilkan semua mahasiswa yang meregistrasi matakuliah - IMK" },
            { question: "Perintah UNIX yang berfungsi untuk mengubah kata kunci adalah .....", options: ["pass", "passwd", "password", "passcode"], answer: "passwd" },
            { question: "Aspek kualitas dari antarmuka pengisian borang adalah .....", options: ["proporsional ukuran form borang dengan layar", "jenis dan warna tampilan aplikasi yang digunakan", "mencerminkan struktur data masukan yang diperlukan oleh sistem", "penggunaan web base yang handal dan cepat dalam mengakses data"], answer: "mencerminkan struktur data masukan yang diperlukan oleh sistem" },
            { question: "Jenis pengisian data pada gambar di bawah ini disebut .....", options: ["combo box", "radio button", "editor box", "list box"], answer: "radio button" },
            { question: "Berikut ini yang merupakan keuntungan dari penggunaan dialog berbasis pengisian borang adalah .....", options: ["dapat menggunakan ruang layar yang besar", "dapat dilakukan pelatihan", "tersedianya berbagai peranti bantu perancangan sistem", "dapat dilakukan navigasi menggunakan kursor"], answer: "dapat dilakukan navigasi menggunakan kursor" },
            { question: "Salah satu masalah dalam pengisian dengan data yang banyak adalah sulitnya berpindah dari satu pilihan ke pilihan lain. Hal ini disebabkan belum adanya teknik .....", options: ["partition", "slicing", "tab", "windowing"], answer: "tab" },
            { question: "Berikut ini yang merupakan pengecekan validasi yang dilakukan oleh sever adalah .....", options: ["pengisian captcha", "pengisian verifikasi password", "pengisian alamat email", "validasi data yang berbintang"], answer: "pengisian captcha" },
            { question: "Salah satu konsekuensi validasi yang dilakukan oleh server adalah .....", options: ["validasi menjadi lebih lambat", "harus terkoneksi dengan internet", "pengguna harus mengisi sesuai dengan data yang diminta", "memerlukan waktu yang cepat"], answer: "validasi menjadi lebih lambat" },
            { question: "Alasan validasi pengecekan dilakukan di server adalah .....", options: ["user dan password lebih aman", "data user dan password disimpan di server", "lebih cepat dilakukan dari pada di sisi klien", "memudahkan administrator melakukan pengecekan login"], answer: "data user dan password disimpan di server" },
            { question: "Salah satu kerugian penggunaan dialog berbasis borang adalah .....", options: ["beban memori rendah", "membutuhkan pengontrol kursor", "navigasi terlihat secara eksplisit", "diperlukan sedikit pelatihan"], answer: "membutuhkan pengontrol kursor" },
            { question: "Jenis pengisian data pada gambar berikut disebut .....", options: ["radio button", "combo box", "check box", "list box"], answer: "check box" },
            { question: "Salah satu tombol yang digunakan untuk pembetulan kesalahan pada saat pengisian borang adalah .....", options: ["space", "backspace", "tab", "ctrl"], answer: "backspace" },
            { question: "Salah satu dokumentasi rancangan adalah .....", options: ["membuat program", "membuat sketsa pada kertas", "running program", "eksekusi sketsa pada aplikasi"], answer: "membuat sketsa pada kertas" },
            { question: "Kategori program aplikasi adalah .....", options: ["public purpose software dan public software", "public purpose software dan recomended software", "special purpose software dan recomended software", "special purpose software dan public software"], answer: "public purpose software dan public software" },
            { question: "Salah satu komponen antarmuka pengguna adalah bahasa .....", options: ["perintah", "daerah", "mesin", "numerik"], answer: "perintah" },
            { question: "Pemilihan ragam dialog dipengaruhi oleh .....", options: ["karakteristik populasi pengguna, tipe dialog yang diperlukan, dan kendala teknologi", "karakteristik populasi perancang, tipe dialog yang diperlukan, dan kendala teknologi", "karakteristik populasi perancang, tipe dialog yang diperlukan, dan kendala alam", "karakteristik populasi pengguna, tipe dialog yang diperlukan, dan kendala alam"], answer: "karakteristik populasi pengguna, tipe dialog yang diperlukan, dan kendala teknologi" },
            { question: "Dalam urutan perancangan, terdapat tahap yang banyak melibatkan pengguna, sehingga pengguna langsung mendapatkan umpan balik yang berupa diskusi informal maupun prototipe dialog yang akan digunakan. Tahap tersebut adalah .....", options: ["pemilihan ragam dialog", "perancangan format pesan", "perancangan struktur dialog", "perancangan penanganan kesalahan"], answer: "perancangan struktur dialog" },
            { question: "Sistem memberi peringatan ketika pengguna melakukan suatu tindakan secara tidak disengaja, misalnya penghapusan berkas, yang dikenal dengan istilah .....", options: ["pemulihan dari kesalahan", "validasi pemasukan data", "penampilan pesan salah", "proteksi pengguna"], answer: "proteksi pengguna" },
            { question: "Salah satu faktor yang harus dipertimbangkan saat perancangan tampilan untuk antarmuka berbasis teks adalah .....", options: ["konsekuensi", "konsistensi", "komputerisasi", "dokumentasi"], answer: "konsistensi" },
            { question: "Salah satu faktor yang harus dipertimbangkan saat perancangan tampilan untuk antarmuka berbasis grafis adalah .....", options: ["struktur internal", "urutan visual dan fokus pengguna", "kosakata grafis yang konsisten dan sesuai", "kesesuaian dengan media"], answer: "kosakata grafis yang konsisten dan sesuai" },
            { question: "Kesalahan sintaksis yang secara langsung akan dideteksi oleh kompiler (compile-time error) merupakan penanganan kesalahan .....", options: ["logika", "penulisan program", "algoritma", "penulisan data"], answer: "penulisan program" },
            { question: "Kesalahan ketika program sedang dijalankan, atau run-time error atau fatal error, adalah penanganan kesalahan .....", options: ["algoritma", "penulisan data", "logika", "penulisan program"], answer: "penulisan data" },
            { question: "Pendokumentasian perancangan berguna sebagai pedoman untuk mengimplementasikan antarmuka, hal tersebut berguna bagi .....", options: ["pemrogram", "pengguna", "penjual", "pembeli"], answer: "pemrogram" },
            { question: "Pendokumentasian perancangan yang berguna untuk membayangkan 'wajah' sistem yang akan dibuat, berguna bagi .....", options: ["pembeli", "penjual", "pemrogram", "pengguna"], answer: "pengguna" },
            { question: "Bagian Lembar Kerja Tampilan (LKT) yang menjelaskan kapan tampilan yang dimaksud akan muncul, dan kapan tampilan itu berubah menjadi tampilan lain, merupakan bagian LKT .....", options: ["nomor lembar kerja", "navigator", "keterangan", "tampilan"], answer: "navigator" },
            { question: "Bagian LKT yang merupakan penjelasan singkat tentang atribut tampilan yang akan dipakai, merupakan bagian LKT .....", options: ["navigator", "tampilan", "keterangan", "nomor lembar kerja"], answer: "keterangan" },
            { question: "Jaring semantik tampilan adalah .....", options: ["Suatu bagan yang dapat memudahkan pemrogram dalam menyesuaikan navigasi pada setiap lembar kerja", "Suatu program yang dapat memudahkan pemrogram dalam menyesuaikan navigasi pada setiap lembar kerja", "Suatu bagan yang dapat memudahkan pengguna dalam menyesuaikan navigasi pada setiap lembar kerja", "Suatu program yang dapat memudahkan pengguna dalam menyesuaikan navigasi pada setiap lembar kerja"], answer: "Suatu bagan yang dapat memudahkan pemrogram dalam menyesuaikan navigasi pada setiap lembar kerja" },
            { question: "Jaring semantik terdiri dari dua komponen yaitu .....", options: ["nomor data dan transisi", "nomor data dan akomodasi", "nomor tampilan dan transisi", "nomor tampilan dan akomodasi"], answer: "nomor tampilan dan transisi" },
            { question: "Pada gambar suatu jaring semantik di bawah ini, terdapat transisi loop, yang berfungsi untuk .....", options: ["nomor tampilan", "keterangan", "meminta konfirmasi pengguna", "peristiwa"], answer: "meminta konfirmasi pengguna" },
            { question: "Berdasarkan LKT pada gambar berikut, kotak yang diberi keterangan 'D' disebut dengan .....", options: ["navigasi", "keterangan", "tampilan", "nomor tampilan"], answer: "keterangan" },
            { question: "Pada gambar di bawah ini, terdapat tanda lingkaran yang bertuliskan T1, T2, T3, T4, dan T5, yang menyatakan .....", options: ["keterangan", "meminta konfirmasi pengguna", "peristiwa", "nomor tampilan"], answer: "nomor tampilan" },
            { question: "Pada gambar berikut, terdapat keterangan tanda panah yang bertuliskan Alt-S, Cetak, Simpan, dan Selesai, yang menyatakan .....", options: ["peristiwa", "keterangan", "nomor tampilan", "meminta konfirmasi pengguna"], answer: "peristiwa" },
            { question: "Salah satu peranti masukan tekstual adalah .....", options: ["mouse", "trackball", "joystick", "keyboard"], answer: "keyboard" },
            { question: "Tombol pada papan ketik dapat dikelompokkan menjadi empat bagian, salah satunya adalah tombol .....", options: ["transisi", "manipulasi", "fungsi", "proses"], answer: "fungsi" },
            { question: "Sebuah papan ketik yang mengambil enam tombol pada baris kedua dari tombol alfanumerik adalah papan ketik dengan tata letak .....", options: ["QWERTY", "Dvorak", "alfabetik", "Klockenberg"], answer: "QWERTY" },
            { question: "Papan ketik yang membebankan tangan kanan lebih dari tangan kiri adalah papan ketik dengan tata letak .....", options: ["QWERTY", "Dvorak", "Klockenberg", "alfabetik"], answer: "Dvorak" },
            { question: "Dua tata letak papan ketik yang memasukkan unsur ergonomik adalah .....", options: ["QWERTY dan Dvorak", "Dvorak dan Klockenberg", "Klockenberg dan alfabetik", "alfabetik dan numerik"], answer: "Dvorak dan Klockenberg" },
            { question: "Peranti untuk menempatkan kursor di suatu posisi pada layar tampilan dan untuk mengambil suatu item informasi untuk dipindahkan ke tempat lain, disebut dengan peranti .....", options: ["pemindah dan pengambil", "pemberi dan penuding", "penuding dan pemindah", "penuding dan pengambil"], answer: "penuding dan pemindah" },
            { question: "Suatu peranti yang banyak digunakan untuk aplikasi dalam bidang computer-aided design (CAD), atau untuk menyalin gambar yang tersedia ke dalam bentuk digital untuk diolah lebih lanjut adalah .....", options: ["digitizing tablet", "joystick", "touch-sensitive panel", "light pen"], answer: "digitizing tablet" },
            { question: "Peranti yang bekerja dengan cara mendeteksi ada tidaknya sentuhan tangan atau stylus langsung ke layar komputer adalah peranti .....", options: ["light pen", "digitizing tablet", "touch-sensitive panel", "joystick"], answer: "touch-sensitive panel" },
            { question: "Pada pertengahan tahun tujuh puluhan dikembangkan jenis layar tampilan berdasarkan teknologi televisi, yang disebut dengan .....", options: ["display list", "raster display", "display program", "electronic gun"], answer: "raster display" },
            { question: "Tipe layar yang dapat menghasilkan teks dan grafik berwarna, termasuk ke dalam kelompok layar tampilan .....", options: ["composite color monitor", "red green blue monitor", "variable frequency monitor", "direct drive monitor"], answer: "red green blue monitor" },
            { question: "Mesin yang berinteraksi dengan manusia, yang dirancang untuk lingkungan yang tetap adalah .....", options: ["ATM", "mobile phone", "PDA", "komputer jinjing (laptop)"], answer: "ATM" },
            { question: "Pengaruh radiasi merupakan contoh kejadian yang perlu diperhatikan dalam merancang lingkungan fisik komputasi, contoh tersebut termasuk ke dalam isu .....", options: ["ruang kerja", "ruang pengguna", "efisiensi", "keamanan"], answer: "keamanan" },
            { question: "Jika perancangan fisik tidak memadai, maka pengguna dapat merasakan kelelahan, kesakitan bahkan cedera. Hal tersebut termasuk ke dalam isu yang perlu diperhatikan dalam merancang lingkungan fisik komputasi, yaitu .....", options: ["pencahayaan", "efisiensi", "ruang pengguna", "keamanan"], answer: "keamanan" },
            { question: "Tutup papan ketik plastik, penutup layar sentuh yang dapat dicuci, merupakan salah satu solusi untuk melindungi peralatan tersebut dari isu .....", options: ["efisiensi", "polusi", "pencahayaan", "keamanan"], answer: "polusi" },
            { question: "Adanya berbagai keluhan pada mata, seperti iritasi, dan ketegangan mata yang makin hari makin bertambah, merupakan pengamatan mengenai aspek ergonomik dari stasiun kerja yang dilakukan oleh .....", options: ["Laubli", "Haider", "Burns", "Norman"], answer: "Laubli" },
            { question: "Semakin lama seseorang bekerja di depan komputer, maka dia akan mendapatkan miopi yang semakin besar, pengamatan tersebut dilakukan oleh .....", options: ["Haider", "Norman", "Laubli", "Burns"], answer: "Haider" },
            { question: "Faktor yang sangat mempengaruhi unjuk kerja operator stasiun kerja, menurut Sauter (1991) adalah .....", options: ["tumpuan punggung dan pinggang", "sudut melihat dan papan ketik", "meja kerja yang stabil", "posisi telapak tangan dan lengan"], answer: "posisi telapak tangan dan lengan" },
            { question: "Pekerjaan operator telepon, pengatur lalu lintas udara, dan petugas pos yang bertugas di bagian surat elektronik adalah pekerjaan yang termasuk pada tipe pekerjaan .....", options: ["pemasukan data", "pekerjaan interaktif", "pengolahan kata", "akuisisi data"], answer: "pekerjaan interaktif" },
            { question: "Bagi petugas reservasi mereka menghadapi dua beban secara bersamaan, yaitu .....", options: ["beban visual dan beban tubuh", "beban otot dan beban visual", "beban visual dan beban otot", "beban otot dan beban tubuh"], answer: "beban otot dan beban visual" },
            { question: "Bagi seorang juru ketik, akan mendapatkan beban kerja yaitu .....", options: ["beban otot dan beban visual", "beban otot dan beban tubuh", "beban visual dan beban tubuh", "beban visual dan beban otot"], answer: "beban otot dan beban visual" },
            { question: "Keluhan pada leher, bahu, dan lengan pada saat Anda berada di depan stasiun kerja, disebabkan oleh .....", options: ["kursi yang tidak memadai", "tinggi meja yang tidak memadai", "sudut telapak tangan yang jelek", "terlalu banyak mengetik"], answer: "tinggi meja yang tidak memadai" },
            { question: "Salah satu cara untuk menghindari adanya kilau yang ditimbulkan oleh layar tampilan yang dapat mengurangi kenyamanan seorang pengguna komputer adalah .....", options: ["memasang filter anti kilau", "menutup layar komputer", "meletakkan layar komputer dalam ruangan gelap", "memasang filter anti debu"], answer: "memasang filter anti kilau" },
            { question: "Tujuan utama perancangan pencahayaan untuk penempatan layar tampilan adalah .....", options: ["mendekati cahaya langsung", "menghadapkan layar pada cahaya pantulannya", "menghindari cahaya langsung", "menghindari pengguna dari pencahayaan yang cukup"], answer: "menghindari cahaya langsung" },
            { question: "Contoh cahaya langsung adalah .....", options: ["kaca", "tembok", "matahari", "lantai"], answer: "matahari" },
            { question: "Cahaya yang dipantulkan dari bahan-bahan yang ada di sekitar layar tampilan, disebut dengan .....", options: ["cahaya langsung", "cahaya ruangan", "cahaya lantai", "cahaya tidak langsung"], answer: "cahaya tidak langsung" },
            { question: "Salah satu faktor yang harus diperhatikan dalam pencahayaan ruang stasiun kerja adalah .....", options: ["gunakan sumber cahaya tak langsung", "menempatkan sumber cahaya di atas kepala", "gunakan sumber cahaya yang sangat terang", "menempatkan sumber cahaya untuk mendapatkan cahaya semaksimal mungkin"], answer: "gunakan sumber cahaya tak langsung" },
            { question: "Untuk mengatasi persoalan bertambah panasnya lingkungan kerja, yaitu dengan .....", options: ["menutup jendela pada ruang kerja Anda", "menggunakan alat pengontrol udara", "menggunakan lampu yang memiliki pencahayaan besar", "menambah lampu pada ruang kerja Anda"], answer: "menggunakan alat pengontrol udara" },
            { question: "Salah satu risiko yang disebabkan kondisi kesehatan saat berada di depan stasiun kerja adalah .....", options: ["kenyamanan", "kedamaian emosi", "kelenturan otot dan persendian", "kelelahan otot dan persendian"], answer: "kelelahan otot dan persendian" },
            { question: "Indra yang bekerja keras selama kita bekerja menggunakan stasiun kerja adalah .....", options: ["hidung", "tangan", "mata", "telinga"], answer: "mata" },
            { question: "Mengubah posisi duduk adalah salah satu kebiasaan pada lingkungan kerja untuk .....", options: ["memberikan kelelahan pada pengguna stasiun kerja", "memberikan kenyamanan pada pengguna stasiun kerja", "memberikan kegundahan pada pengguna stasiun kerja", "memberikan kegelisahan pada pengguna stasiun kerja"], answer: "memberikan kenyamanan pada pengguna stasiun kerja" },
        ];

        const quizContainer = document.getElementById('quiz-container');
        const submitBtn = document.getElementById('submit-btn');
        const scoreContainer = document.getElementById('score-container');
        const scoreSpan = document.getElementById('score');
        const restartBtn = document.getElementById('restart-btn');

        let currentQuestions = [];
        const numberOfQuestions = 50;

        function shuffleArray(array) {
            for (let i = array.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [array[i], array[j]] = [array[j], array[i]];
            }
            return array;
        }

        function startQuiz() {
            quizContainer.innerHTML = '';
            scoreContainer.style.display = 'none';
            submitBtn.style.display = 'block';

            const shuffledQuestions = shuffleArray([...questionsData]); // Create a shallow copy to avoid modifying original
            currentQuestions = shuffledQuestions.slice(0, numberOfQuestions);
            
            currentQuestions.forEach((q, index) => {
                const questionBlock = document.createElement('div');
                questionBlock.classList.add('question-block');
                
                const questionText = document.createElement('div');
                questionText.classList.add('question-text');
                // Removed unicorn emoji, added a simple star icon as per previous iteration
                questionText.innerHTML = `<span class="icon">&#10024;</span> ${index + 1}. ${q.question}`;
                questionBlock.appendChild(questionText);

                const optionsDiv = document.createElement('div');
                optionsDiv.classList.add('options');
                q.options.forEach((option, optionIndex) => {
                    const label = document.createElement('label');
                    const input = document.createElement('input');
                    input.type = 'radio';
                    input.name = `question${index}`;
                    input.value = option;
                    label.appendChild(input);
                    label.appendChild(document.createTextNode(option));
                    optionsDiv.appendChild(label);
                });
                questionBlock.appendChild(optionsDiv);
                quizContainer.appendChild(questionBlock);
            });
        }

        function submitQuiz() {
            let score = 0;
            currentQuestions.forEach((q, index) => {
                const selectedOption = document.querySelector(`input[name="question${index}"]:checked`);
                const questionBlock = quizContainer.children[index];
                const optionsLabels = questionBlock.querySelectorAll('.options label');

                optionsLabels.forEach(label => {
                    label.classList.remove('correct-answer', 'wrong-answer');
                });

                if (selectedOption) {
                    if (selectedOption.value === q.answer) {
                        score++;
                        selectedOption.parentElement.classList.add('correct-answer');
                    } else {
                        selectedOption.parentElement.classList.add('wrong-answer');
                        // Highlight the correct answer
                        optionsLabels.forEach(label => {
                            if (label.textContent.trim() === q.answer) {
                                label.classList.add('correct-answer');
                            }
                        });
                    }
                } else {
                    // If no answer selected, just show the correct one
                    optionsLabels.forEach(label => {
                        if (label.textContent.trim() === q.answer) {
                            label.classList.add('correct-answer');
                        }
                    });
                }
            });

            scoreSpan.textContent = score;
            scoreContainer.style.display = 'block';
            submitBtn.style.display = 'none';
        }

        submitBtn.addEventListener('click', submitQuiz);
        restartBtn.addEventListener('click', startQuiz);

        // Initialize the quiz
        startQuiz();
    </script>
</body>
</html>
