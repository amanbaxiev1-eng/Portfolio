<!DOCTYPE html>
<html lang="kaa">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mening Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #0a0a0a;
            color: #fff;
            overflow-x: hidden;
        }

        #python-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            overflow: hidden;
            opacity: 0.3;
        }

        .code-line {
            position: absolute;
            font-family: 'Courier New', monospace;
            font-size: 14px;
            white-space: nowrap;
            color: #4fc3f7;
            text-shadow: 0 0 10px rgba(79, 195, 247, 0.5);
        }

        .keyword { color: #ff6b9d; }
        .string { color: #c3e88d; }
        .function { color: #82aaff; }
        .comment { color: #546e7a; font-style: italic; }

        .container {
            position: relative;
            z-index: 1;
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        header {
            text-align: center;
            padding: 100px 20px 50px;
            background: linear-gradient(135deg, rgba(79, 195, 247, 0.1) 0%, rgba(255, 107, 157, 0.1) 100%);
            border-radius: 20px;
            margin-bottom: 50px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 4px solid #4fc3f7;
            margin-bottom: 20px;
            box-shadow: 0 0 30px rgba(79, 195, 247, 0.5);
        }

        h1 {
            font-size: 3em;
            margin-bottom: 10px;
            background: linear-gradient(45deg, #4fc3f7, #ff6b9d);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .tagline {
            font-size: 1.3em;
            color: #b0bec5;
            margin-bottom: 30px;
        }

        .social-links {
            display: flex;
            gap: 20px;
            justify-content: center;
            margin-top: 20px;
        }

        .social-links a {
            color: #4fc3f7;
            text-decoration: none;
            padding: 10px 20px;
            border: 2px solid #4fc3f7;
            border-radius: 25px;
            transition: all 0.3s;
        }

        .social-links a:hover {
            background: #4fc3f7;
            color: #0a0a0a;
            transform: translateY(-3px);
            box-shadow: 0 5px 20px rgba(79, 195, 247, 0.5);
        }

        section {
            background: rgba(255, 255, 255, 0.05);
            padding: 40px;
            margin-bottom: 30px;
            border-radius: 20px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        h2 {
            font-size: 2.5em;
            margin-bottom: 30px;
            color: #4fc3f7;
            text-align: center;
        }

        .about-content {
            font-size: 1.1em;
            line-height: 1.8;
            color: #cfd8dc;
        }

        .skills {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .skill {
            background: rgba(79, 195, 247, 0.1);
            padding: 15px;
            border-radius: 10px;
            text-align: center;
            border: 1px solid #4fc3f7;
            transition: all 0.3s;
        }

        .skill:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 20px rgba(79, 195, 247, 0.3);
        }

        .projects {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .project-card {
            background: rgba(255, 255, 255, 0.05);
            padding: 30px;
            border-radius: 15px;
            border: 1px solid rgba(79, 195, 247, 0.3);
            transition: all 0.3s;
        }

        .project-card:hover {
            transform: translateY(-10px);
            border-color: #4fc3f7;
            box-shadow: 0 10px 30px rgba(79, 195, 247, 0.3);
        }

        .project-card h3 {
            color: #ff6b9d;
            margin-bottom: 15px;
            font-size: 1.5em;
        }

        .project-card p {
            color: #b0bec5;
            margin-bottom: 15px;
            line-height: 1.6;
        }

        .project-link {
            display: inline-block;
            color: #4fc3f7;
            text-decoration: none;
            padding: 8px 20px;
            border: 2px solid #4fc3f7;
            border-radius: 20px;
            transition: all 0.3s;
        }

        .project-link:hover {
            background: #4fc3f7;
            color: #0a0a0a;
        }

        .contact-form {
            max-width: 600px;
            margin: 0 auto;
        }

        .form-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            margin-bottom: 8px;
            color: #4fc3f7;
        }

        input, textarea {
            width: 100%;
            padding: 12px;
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(79, 195, 247, 0.3);
            border-radius: 8px;
            color: #fff;
            font-size: 16px;
        }

        input:focus, textarea:focus {
            outline: none;
            border-color: #4fc3f7;
            box-shadow: 0 0 10px rgba(79, 195, 247, 0.3);
        }

        button {
            background: linear-gradient(45deg, #4fc3f7, #ff6b9d);
            color: #fff;
            padding: 15px 40px;
            border: none;
            border-radius: 25px;
            font-size: 18px;
            cursor: pointer;
            transition: all 0.3s;
        }

        button:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 20px rgba(79, 195, 247, 0.5);
        }

        footer {
            text-align: center;
            padding: 30px;
            color: #546e7a;
            margin-top: 50px;
        }

        @media (max-width: 768px) {
            h1 { font-size: 2em; }
            h2 { font-size: 1.8em; }
            .projects { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>
    <div id="python-bg"></div>

    <div class="container">
        <header>
            <div class="profile-img" style="background: linear-gradient(135deg, #4fc3f7, #ff6b9d); display: flex; align-items: center; justify-content: center; font-size: 4em;">👨‍💻</div>
            <h1>Sizdiń Atıńız</h1>
            <p class="tagline">Python Rawajlandırıwshı | Web Rawajlandırıwshı | Baǵdarlamashı</p>
            <div class="social-links">
                <a href="#" target="_blank">GitHub</a>
                <a href="#" target="_blank">LinkedIn</a>
                <a href="#" target="_blank">Telegram</a>
            </div>
        </header>

        <section id="about">
            <h2>Men haqqımda</h2>
            <div class="about-content">
                <p>Sálem! Men professional baǵdarlamashıman, Python hám web texnologiyaları menen islewdi jaqsı kóremen. Men házirgi zaman hám funktsional web-saytlar jaratıwda tájiriybem bar.</p>
                <br>
                <p>Meniń maqsetim - joqarı sıpatlı hám paydalalanıwshılarǵa qulay baǵdarlamalı mahsulotlar jaratıw. Hár bir loyihaga kreativ jaqınlasıw hám professional kórinisti támiyinleymen.</p>
                
                <div class="skills">
                    <div class="skill">Python</div>
                    <div class="skill">Django</div>
                    <div class="skill">Flask</div>
                    <div class="skill">HTML/CSS</div>
                    <div class="skill">JavaScript</div>
                    <div class="skill">React</div>
                    <div class="skill">SQL</div>
                    <div class="skill">Git</div>
                </div>
            </div>
        </section>

        <section id="projects">
            <h2>Loyihalarım</h2>
            <div class="projects">
                <div class="project-card">
                    <h3>E-commerce Platforma</h3>
                    <p>Django hám React járdeminde jaratılǵan tolıq funktsional onlayn dúkan. Mahsulotlar katalogı, sebetshik hám tólem sistemi bar.</p>
                    <a href="#" class="project-link">Kóriw →</a>
                </div>

                <div class="project-card">
                    <h3>Blog Platforması</h3>
                    <p>Flask menen jaratılǵan házirgi zaman blog sistemi. Paydalalanıwshılar dizimnen ótiw, maqala jazıw hám pikir qaldırıw múmkin.</p>
                    <a href="#" class="project-link">Kóriw →</a>
                </div>

                <div class="project-card">
                    <h3>Wazıypa Basqarıwshı</h3>
                    <p>Wazıypaları basqarıw ushın web qosımsha. Kanban board stilinde, real-time jańalanıwlar menen.</p>
                    <a href="#" class="project-link">Kóriw →</a>
                </div>

                <div class="project-card">
                    <h3>Hawa Rayı Qosımshası</h3>
                    <p>API integratsiyası menen hawa rayı maǵlıwmatların kórsetiwshi qosımsha. Qala boyınsha izlew hám 5 kúnlik prognoz.</p>
                    <a href="#" class="project-link">Kóriw →</a>
                </div>

                <div class="project-card">
                    <h3>Portfolio Jaratıwshı</h3>
                    <p>Baǵdarlamashılar ushın portfolio jaratıw qoralı. Shablonlar hám dinamik mazmun basqarıw sistemi.</p>
                    <a href="#" class="project-link">Kóriw →</a>
                </div>

                <div class="project-card">
                    <h3>Chat Qosımshası</h3>
                    <p>WebSocket texnologiyası járdeminde real-time chat qosımshası. Gruppa xabarlama hám fayl jiberiw múmkinshiligi.</p>
                    <a href="#" class="project-link">Kóriw →</a>
                </div>
            </div>
        </section>

        <section id="contact">
            <h2>Baylanıs</h2>
            <div class="contact-form">
                <div class="form-group">
                    <label for="name">Atıńız</label>
                    <input type="text" id="name" placeholder="Atıńızdı kirgiziń">
                </div>
                <div class="form-group">
                    <label for="email">Email</label>
                    <input type="email" id="email" placeholder="Email mánzilinizdi kirgiziń">
                </div>
                <div class="form-group">
                    <label for="message">Xabar</label>
                    <textarea id="message" rows="5" placeholder="Xabarıńızdı jazıń"></textarea>
                </div>
                <button type="button" onclick="sendMessage()">Jiberiw</button>
            </div>
        </section>

        <footer>
            <p>&copy; 2025 Sizdiń Atıńız. Barlıq huqıqlar qorǵalǵan.</p>
        </footer>
    </div>

    <!-- Admin Login Button (Sag tómende jasırın) -->
    <div id="adminLoginBtn" style="position: fixed; bottom: 20px; right: 20px; width: 50px; height: 50px; background: rgba(79, 195, 247, 0.1); border: 2px solid rgba(79, 195, 247, 0.3); border-radius: 50%; cursor: pointer; display: flex; align-items: center; justify-content: center; transition: all 0.3s; z-index: 1000;" onclick="showLoginModal()">
        <span style="font-size: 24px;">🔒</span>
    </div>

    <!-- Login Modal -->
    <div id="loginModal" style="display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.8); z-index: 9998; display: none; align-items: center; justify-content: center;">
        <div style="background: linear-gradient(135deg, rgba(10,10,10,0.95) 0%, rgba(30,30,30,0.95) 100%); padding: 40px; border-radius: 20px; border: 2px solid rgba(79,195,247,0.3); box-shadow: 0 20px 60px rgba(0,0,0,0.5); max-width: 400px; width: 90%;">
            <h3 style="color: #4fc3f7; margin-bottom: 30px; text-align: center; font-size: 2em;">Admin Kiriwi</h3>
            <div style="margin-bottom: 20px;">
                <label style="display: block; color: #4fc3f7; margin-bottom: 8px;">Login:</label>
                <input type="text" id="loginUsername" placeholder="Login kirgiziń" style="width: 100%; padding: 12px; background: rgba(255,255,255,0.1); border: 1px solid rgba(79,195,247,0.3); border-radius: 8px; color: #fff; font-size: 16px;">
            </div>
            <div style="margin-bottom: 30px;">
                <label style="display: block; color: #4fc3f7; margin-bottom: 8px;">Parol:</label>
                <input type="password" id="loginPassword" placeholder="Parol kirgiziń" style="width: 100%; padding: 12px; background: rgba(255,255,255,0.1); border: 1px solid rgba(79,195,247,0.3); border-radius: 8px; color: #fff; font-size: 16px;">
            </div>
            <div style="display: flex; gap: 15px;">
                <button onclick="attemptLogin()" style="flex: 1; background: linear-gradient(45deg, #4fc3f7, #ff6b9d); padding: 12px; border: none; border-radius: 8px; color: #fff; font-size: 16px; cursor: pointer;">Kiriw</button>
                <button onclick="closeLoginModal()" style="flex: 1; background: rgba(255,107,157,0.2); padding: 12px; border: 1px solid #ff6b9d; border-radius: 8px; color: #ff6b9d; font-size: 16px; cursor: pointer;">Bıykar etıw</button>
            </div>
        </div>
    </div>

    <!-- Admin Panel (Jasırın) -->
    <div id="adminPanel" style="display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.95); z-index: 9999; overflow-y: auto;">
        <div style="max-width: 900px; margin: 50px auto; padding: 30px;">
            <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 30px;">
                <h2 style="color: #4fc3f7; font-size: 2.5em;">⚙️ Admin Panel</h2>
                <button onclick="closeAdmin()" style="background: #ff6b9d; padding: 10px 30px; border: none; border-radius: 8px; color: #fff; cursor: pointer; font-size: 16px;">Shıǵıw</button>
            </div>

            <!-- Shaxsıy maǵlıwmatlar -->
            <div style="background: rgba(255,255,255,0.05); padding: 30px; border-radius: 15px; margin-bottom: 30px; border: 1px solid rgba(79,195,247,0.3);">
                <h3 style="color: #ff6b9d; margin-bottom: 20px; font-size: 1.8em;">Shaxsıy Maǵlıwmatlar</h3>
                
                <!-- Profil resimi -->
                <div style="margin-bottom: 25px;">
                    <label style="display: block; color: #4fc3f7; margin-bottom: 12px; font-size: 16px;">Profil Resimi:</label>
                    <div style="display: flex; gap: 20px; align-items: center; flex-wrap: wrap;">
                        <div id="previewImage" style="width: 120px; height: 120px; border-radius: 50%; border: 3px solid #4fc3f7; display: flex; align-items: center; justify-content: center; font-size: 3em; background: linear-gradient(135deg, #4fc3f7, #ff6b9d); overflow: hidden;">
                            👨‍💻
                        </div>
                        <div style="flex: 1; min-width: 200px;">
                            <div style="margin-bottom: 15px;">
                                <label style="display: block; color: #b0bec5; margin-bottom: 8px; font-size: 14px;">Resim URL-ın kirgiziń:</label>
                                <input type="text" id="adminImageUrl" placeholder="https://example.com/image.jpg" style="width: 100%; padding: 10px; background: rgba(255,255,255,0.1); border: 1px solid rgba(79,195,247,0.3); border-radius: 6px; color: #fff; font-size: 14px;">
                            </div>
                            <div>
                                <label style="display: block; color: #b0bec5; margin-bottom: 8px; font-size: 14px;">Yamasa emoji saylań:</label>
                                <select id="adminEmoji" style="width: 100%; padding: 10px; background: rgba(255,255,255,0.1); border: 1px solid rgba(79,195,247,0.3); border-radius: 6px; color: #fff; font-size: 20px; cursor: pointer;">
                                    <option value="👨‍💻">👨‍💻 Dasturchi</option>
                                    <option value="👩‍💻">👩‍💻 Qız dasturchi</option>
                                    <option value="🚀">🚀 Raketa</option>
                                    <option value="💻">💻 Kompyuter</option>
                                    <option value="🎯">🎯 Maqset</option>
                                    <option value="⚡">⚡ Tez</option>
                                    <option value="🔥">🔥 Ot</option>
                                    <option value="💡">💡 Ideya</option>
                                    <option value="🌟">🌟 Jultız</option>
                                    <option value="🎨">🎨 Dizayn</option>
                                </select>
                            </div>
                            <button onclick="previewProfileImage()" style="margin-top: 10px; background: rgba(79,195,247,0.2); padding: 8px 20px; border: 1px solid #4fc3f7; border-radius: 6px; color: #4fc3f7; cursor: pointer; font-size: 14px;">Aldın ala kóriw</button>
                        </div>
                    </div>
                    <p style="color: #546e7a; font-size: 13px; margin-top: 10px; font-style: italic;">* Resim URL-ın kirgizseńiz, emoji orınına resim kórsetiledi</p>
                </div>

                <div style="margin-bottom: 20px;">
                    <label style="display: block; color: #4fc3f7; margin-bottom: 8px;">Atıńız:</label>
                    <input type="text" id="adminName" placeholder="Atıńızdı kirgiziń" style="width: 100%; padding: 12px; background: rgba(255,255,255,0.1); border: 1px solid rgba(79,195,247,0.3); border-radius: 8px; color: #fff; font-size: 16px;">
                </div>
                <div style="margin-bottom: 20px;">
                    <label style="display: block; color: #4fc3f7; margin-bottom: 8px;">Qısqasha sıpatlama:</label>
                    <input type="text" id="adminTagline" placeholder="Máselen: Python Rawajlandırıwshı" style="width: 100%; padding: 12px; background: rgba(255,255,255,0.1); border: 1px solid rgba(79,195,247,0.3); border-radius: 8px; color: #fff; font-size: 16px;">
                </div>
                <div style="margin-bottom: 20px;">
                    <label style="display: block; color: #4fc3f7; margin-bottom: 8px;">Men haqqımda (1-ábzats):</label>
                    <textarea id="adminAbout1" rows="3" style="width: 100%; padding: 12px; background: rgba(255,255,255,0.1); border: 1px solid rgba(79,195,247,0.3); border-radius: 8px; color: #fff; font-size: 16px;"></textarea>
                </div>
                <div style="margin-bottom: 20px;">
                    <label style="display: block; color: #4fc3f7; margin-bottom: 8px;">Men haqqımda (2-ábzats):</label>
                    <textarea id="adminAbout2" rows="3" style="width: 100%; padding: 12px; background: rgba(255,255,255,0.1); border: 1px solid rgba(79,195,247,0.3); border-radius: 8px; color: #fff; font-size: 16px;"></textarea>
                </div>
            </div>

            <!-- Loyihalar -->
            <div style="background: rgba(255,255,255,0.05); padding: 30px; border-radius: 15px; margin-bottom: 30px; border: 1px solid rgba(79,195,247,0.3);">
                <h3 style="color: #ff6b9d; margin-bottom: 20px; font-size: 1.8em;">Loyihalar</h3>
                <div id="adminProjectsList"></div>
                <button onclick="addNewProject()" style="background: linear-gradient(45deg, #4fc3f7, #ff6b9d); padding: 12px 30px; margin-top: 20px;">+ Jańa Loyiha Qosıw</button>
            </div>

            <button onclick="saveAdminData()" style="background: linear-gradient(45deg, #4fc3f7, #ff6b9d); padding: 15px 50px; font-size: 18px; width: 100%;">Saqlaw</button>
        </div>
    </div>

    <script>
        // Admin login hám parol
        const ADMIN_USERNAME = "admin";
        const ADMIN_PASSWORD = "admin2025";
        
        // Login modal funkciyaları
        function showLoginModal() {
            document.getElementById('loginModal').style.display = 'flex';
        }

        function closeLoginModal() {
            document.getElementById('loginModal').style.display = 'none';
            document.getElementById('loginUsername').value = '';
            document.getElementById('loginPassword').value = '';
        }

        function attemptLogin() {
            const username = document.getElementById('loginUsername').value;
            const password = document.getElementById('loginPassword').value;
            
            if (username === ADMIN_USERNAME && password === ADMIN_PASSWORD) {
                closeLoginModal();
                openAdmin();
            } else {
                alert('Login yamasa parol qáte!');
            }
        }

        // Enter knopkasın basqanda login
        document.addEventListener('DOMContentLoaded', function() {
            const loginPassword = document.getElementById('loginPassword');
            if (loginPassword) {
                loginPassword.addEventListener('keypress', function(e) {
                    if (e.key === 'Enter') {
                        attemptLogin();
                    }
                });
            }
        });
        
        // Ma'lumotlar saxlawshı
        let portfolioData = {
            name: "Sizdiń Atıńız",
            tagline: "Python Rawajlandırıwshı | Web Rawajlandırıwshı | Baǵdarlamashı",
            about1: "Sálem! Men professional baǵdarlamashıman, Python hám web texnologiyaları menen islewdi jaqsı kóremen. Men házirgi zaman hám funktsional web-saytlar jaratıwda tájiriybem bar.",
            about2: "Meniń maqsetim - joqarı sıpatlı hám paydalalanıwshılarǵa qulay baǵdarlamalı mahsulotlar jaratıw. Hár bir loyihaga kreativ jaqınlasıw hám professional kórinisti támiyinleymen.",
            projects: [
                {
                    title: "E-commerce Platforma",
                    description: "Django hám React járdeminde jaratılǵan tolıq funktsional onlayn dúkan. Mahsulotlar katalogı, sebetshik hám tólem sistemi bar.",
                    link: "#"
                },
                {
                    title: "Blog Platforması",
                    description: "Flask menen jaratılǵan házirgi zaman blog sistemi. Paydalalanıwshılar dizimnen ótiw, maqala jazıw hám pikir qaldırıw múmkin.",
                    link: "#"
                },
                {
                    title: "Wazıypa Basqarıwshı",
                    description: "Wazıypaları basqarıw ushın web qosımsha. Kanban board stilinde, real-time jańalanıwlar menen.",
                    link: "#"
                },
                {
                    title: "Hawa Rayı Qosımshası",
                    description: "API integratsiyası menen hawa rayı maǵlıwmatların kórsetiwshi qosımsha. Qala boyınsha izlew hám 5 kúnlik prognoz.",
                    link: "#"
                },
                {
                    title: "Portfolio Jaratıwshı",
                    description: "Baǵdarlamashılar ushın portfolio jaratıw qoralı. Shablonlar hám dinamik mazmun basqarıw sistemi.",
                    link: "#"
                },
                {
                    title: "Chat Qosımshası",
                    description: "WebSocket texnologiyası járdeminde real-time chat qosımshası. Gruppa xabarlama hám fayl jiberiw múmkinshiligi.",
                    link: "#"
                }
            ]
        };

        // Admin panel ashıw
        window.addEventListener('load', function() {
            updatePage();
        });

        function openAdmin() {
            document.getElementById('adminPanel').style.display = 'block';
            document.getElementById('adminLoginBtn').style.display = 'none';
            document.getElementById('adminName').value = portfolioData.name;
            document.getElementById('adminTagline').value = portfolioData.tagline;
            document.getElementById('adminImageUrl').value = portfolioData.profileImage;
            document.getElementById('adminEmoji').value = portfolioData.profileEmoji;
            document.getElementById('adminAbout1').value = portfolioData.about1;
            document.getElementById('adminAbout2').value = portfolioData.about2;
            updatePreview();
            loadAdminProjects();
        }

        function previewProfileImage() {
            updatePreview();
        }

        function updatePreview() {
            const imageUrl = document.getElementById('adminImageUrl').value;
            const emoji = document.getElementById('adminEmoji').value;
            const preview = document.getElementById('previewImage');
            
            if (imageUrl && imageUrl.trim() !== '') {
                preview.style.background = 'none';
                preview.innerHTML = `<img src="${imageUrl}" style="width: 100%; height: 100%; object-fit: cover;" onerror="this.style.display='none'; this.parentElement.innerHTML='❌'; this.parentElement.style.background='linear-gradient(135deg, #4fc3f7, #ff6b9d)';">`;
            } else {
                preview.style.background = 'linear-gradient(135deg, #4fc3f7, #ff6b9d)';
                preview.innerHTML = emoji;
            }
        }

        // Emoji saylawda aldın ala kóriw
        document.addEventListener('DOMContentLoaded', function() {
            const emojiSelect = document.getElementById('adminEmoji');
            if (emojiSelect) {
                emojiSelect.addEventListener('change', updatePreview);
            }
            const imageUrlInput = document.getElementById('adminImageUrl');
            if (imageUrlInput) {
                imageUrlInput.addEventListener('input', function() {
                    // Awtomatik preview faqat URL tolıq kórinsede
                    if (this.value.startsWith('http')) {
                        updatePreview();
                    }
                });
            }
        });

        function closeAdmin() {
            document.getElementById('adminPanel').style.display = 'none';
            document.getElementById('adminLoginBtn').style.display = 'flex';
        }

        function loadAdminProjects() {
            const container = document.getElementById('adminProjectsList');
            container.innerHTML = '';
            
            portfolioData.projects.forEach((project, index) => {
                const projectDiv = document.createElement('div');
                projectDiv.style.cssText = 'background: rgba(255,255,255,0.03); padding: 20px; border-radius: 10px; margin-bottom: 20px; border: 1px solid rgba(79,195,247,0.2);';
                projectDiv.innerHTML = `
                    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 15px;">
                        <h4 style="color: #4fc3f7; font-size: 1.3em;">Loyiha ${index + 1}</h4>
                        <button onclick="removeProject(${index})" style="background: #ff6b9d; padding: 8px 20px; font-size: 14px;">Óshiriw</button>
                    </div>
                    <div style="margin-bottom: 15px;">
                        <label style="display: block; color: #4fc3f7; margin-bottom: 5px; font-size: 14px;">Atı:</label>
                        <input type="text" id="projectTitle${index}" value="${project.title}" style="width: 100%; padding: 10px; background: rgba(255,255,255,0.1); border: 1px solid rgba(79,195,247,0.3); border-radius: 6px; color: #fff;">
                    </div>
                    <div style="margin-bottom: 15px;">
                        <label style="display: block; color: #4fc3f7; margin-bottom: 5px; font-size: 14px;">Sıpatlama:</label>
                        <textarea id="projectDesc${index}" rows="3" style="width: 100%; padding: 10px; background: rgba(255,255,255,0.1); border: 1px solid rgba(79,195,247,0.3); border-radius: 6px; color: #fff;">${project.description}</textarea>
                    </div>
                    <div style="margin-bottom: 15px;">
                        <label style="display: block; color: #4fc3f7; margin-bottom: 5px; font-size: 14px;">Link:</label>
                        <input type="text" id="projectLink${index}" value="${project.link}" placeholder="https://..." style="width: 100%; padding: 10px; background: rgba(255,255,255,0.1); border: 1px solid rgba(79,195,247,0.3); border-radius: 6px; color: #fff;">
                    </div>
                `;
                container.appendChild(projectDiv);
            });
        }

        function addNewProject() {
            portfolioData.projects.push({
                title: "Jańa Loyiha",
                description: "Loyiha sıpatlaması",
                link: "#"
            });
            loadAdminProjects();
        }

        function removeProject(index) {
            if (confirm('Bul loyihanı óshirgińiz keledi me?')) {
                portfolioData.projects.splice(index, 1);
                loadAdminProjects();
            }
        }

        function saveAdminData() {
            // Shaxsıy maǵlıwmatlar
            portfolioData.name = document.getElementById('adminName').value;
            portfolioData.tagline = document.getElementById('adminTagline').value;
            portfolioData.profileImage = document.getElementById('adminImageUrl').value;
            portfolioData.profileEmoji = document.getElementById('adminEmoji').value;
            portfolioData.about1 = document.getElementById('adminAbout1').value;
            portfolioData.about2 = document.getElementById('adminAbout2').value;
            
            // Loyihalar
            portfolioData.projects.forEach((project, index) => {
                project.title = document.getElementById(`projectTitle${index}`).value;
                project.description = document.getElementById(`projectDesc${index}`).value;
                project.link = document.getElementById(`projectLink${index}`).value;
            });
            
            updatePage();
            closeAdmin();
            alert('Maǵlıwmatlar saqlandı!');
        }

        function updatePage() {
            // Bas bet maǵlıwmatların jańalaw
            document.querySelector('header h1').textContent = portfolioData.name;
            document.querySelector('header .tagline').textContent = portfolioData.tagline;
            
            // Profil resimin jańalaw
            const profileImg = document.querySelector('.profile-img');
            if (portfolioData.profileImage && portfolioData.profileImage.trim() !== '') {
                profileImg.style.background = 'none';
                profileImg.style.fontSize = '1em';
                profileImg.innerHTML = `<img src="${portfolioData.profileImage}" style="width: 100%; height: 100%; object-fit: cover; border-radius: 50%;" onerror="this.style.display='none'; this.parentElement.innerHTML='${portfolioData.profileEmoji}'; this.parentElement.style.fontSize='4em'; this.parentElement.style.background='linear-gradient(135deg, #4fc3f7, #ff6b9d)';">`;
            } else {
                profileImg.style.background = 'linear-gradient(135deg, #4fc3f7, #ff6b9d)';
                profileImg.style.fontSize = '4em';
                profileImg.innerHTML = portfolioData.profileEmoji;
            }
            
            // Men haqqımda
            const aboutContent = document.querySelector('#about .about-content');
            aboutContent.innerHTML = `
                <p>${portfolioData.about1}</p>
                <br>
                <p>${portfolioData.about2}</p>
                <div class="skills">
                    <div class="skill">Python</div>
                    <div class="skill">Django</div>
                    <div class="skill">Flask</div>
                    <div class="skill">HTML/CSS</div>
                    <div class="skill">JavaScript</div>
                    <div class="skill">React</div>
                    <div class="skill">SQL</div>
                    <div class="skill">Git</div>
                </div>
            `;
            
            // Loyihalar
            const projectsContainer = document.querySelector('#projects .projects');
            projectsContainer.innerHTML = '';
            portfolioData.projects.forEach(project => {
                const projectCard = document.createElement('div');
                projectCard.className = 'project-card';
                projectCard.innerHTML = `
                    <h3>${project.title}</h3>
                    <p>${project.description}</p>
                    <a href="${project.link}" class="project-link" ${project.link.startsWith('http') ? 'target="_blank"' : ''}>Kóriw →</a>
                `;
                projectsContainer.appendChild(projectCard);
            });
            
            // Footer
            document.querySelector('footer p').textContent = `© 2025 ${portfolioData.name}. Barlıq huqıqlar qorǵalǵan.`;
        }

        // Python kod animatsiyasi
        const pythonCode = [
            '<span class="keyword">def</span> <span class="function">create_portfolio</span>():',
            '    <span class="comment"># Initialize portfolio data</span>',
            '    portfolio = {',
            '        <span class="string">"name"</span>: <span class="string">"Developer"</span>,',
            '        <span class="string">"skills"</span>: [<span class="string">"Python"</span>, <span class="string">"Django"</span>, <span class="string">"Flask"</span>]',
            '    }',
            '    <span class="keyword">return</span> portfolio',
            '',
            '<span class="keyword">class</span> <span class="function">WebDeveloper</span>:',
            '    <span class="keyword">def</span> <span class="function">__init__</span>(self, name):',
            '        self.name = name',
            '        self.projects = []',
            '    ',
            '    <span class="keyword">def</span> <span class="function">add_project</span>(self, project):',
            '        self.projects.append(project)',
            '        <span class="keyword">print</span>(<span class="string">f"Added {project}"</span>)',
            '',
            '<span class="keyword">for</span> i <span class="keyword">in</span> range(10):',
            '    <span class="keyword">print</span>(<span class="string">f"Building amazing projects..."</span>)',
            '',
            '<span class="keyword">import</span> asyncio',
            '<span class="keyword">async def</span> <span class="function">fetch_data</span>():',
            '    <span class="keyword">await</span> asyncio.sleep(1)',
            '    <span class="keyword">return</span> <span class="string">"Success!"</span>'
        ];

        function createCodeLine() {
            const bg = document.getElementById('python-bg');
            const line = document.createElement('div');
            line.className = 'code-line';
            line.innerHTML = pythonCode[Math.floor(Math.random() * pythonCode.length)];
            
            const startX = Math.random() * window.innerWidth;
            const startY = -50;
            const speed = 20 + Math.random() * 30;
            
            line.style.left = startX + 'px';
            line.style.top = startY + 'px';
            
            bg.appendChild(line);
            
            const animation = setInterval(() => {
                const currentTop = parseFloat(line.style.top);
                if (currentTop > window.innerHeight) {
                    clearInterval(animation);
                    bg.removeChild(line);
                } else {
                    line.style.top = (currentTop + speed / 60) + 'px';
                }
            }, 1000 / 60);
        }

        setInterval(createCodeLine, 300);

        function sendMessage() {
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const message = document.getElementById('message').value;
            
            if (name && email && message) {
                alert('Raxmet! Xabarıńız qabıl etildi. Tez arada sizge juwap beremiz.');
                document.getElementById('name').value = '';
                document.getElementById('email').value = '';
                document.getElementById('message').value = '';
            } else {
                alert('Iltimas, barlıq maydanların toltırıń.');
            }
        }

        // Smooth scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth' });
                }
            });
        });
    </script>
</body>
</html>
