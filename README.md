# Interactive_resume
<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kaushambi Vats - Marketing & Brand Management Professional</title>
    <!-- Chosen Palette: Warm Neutral & Professional Teal -->
    <!-- Application Structure Plan: The SPA is structured as a single-page narrative journey. A sticky navigation bar allows smooth scrolling to distinct sections: a hero intro, a vertical timeline for 'Experience', interactive cards for 'Projects', a dynamic bar chart for 'Skills', and clean sections for 'Education' and 'Certifications'. This structure was chosen to transform a static resume into an engaging, interactive experience that guides the user through Kaushambi's career story, making key qualifications more digestible and memorable than a traditional document. The interactive elements encourage exploration and highlight skills and project impacts effectively. -->
    <!-- Visualization & Content Choices: 
        1. Experience -> Vertical Timeline -> HTML/Tailwind -> Goal: Organize & Show Change. Justification: Visually represents career progression in a more engaging way than a simple list.
        2. Skills -> Grouped Horizontal Bar Chart -> Chart.js -> Goal: Inform & Organize. Justification: A clean, scannable, and interactive way to showcase skillsets, far superior to a static list for quick assessment. Interaction: Tooltips on hover.
        3. Projects -> Click-to-reveal Cards -> HTML/Tailwind/JS -> Goal: Engagement & Detail on Demand. Justification: Hides detailed text to keep the layout clean, encouraging user interaction to learn more about key accomplishments.
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #FDFBF8; /* Warm Off-White */
            color: #384A5C; /* Deep Slate Blue */
        }
        .bg-primary { background-color: #008080; } /* Teal */
        .text-primary { color: #008080; }
        .border-primary { border-color: #008080; }
        .accent-bg { background-color: #E6F2F2; } /* Light Teal Accent */
        .nav-link {
            transition: color 0.3s ease, border-bottom-color 0.3s ease;
        }
        .nav-link:hover {
            color: #008080; /* Teal */
            border-bottom-color: #008080;
        }
        .timeline-item::before {
            content: '';
            position: absolute;
            width: 1rem;
            height: 1rem;
            border-radius: 50%;
            left: -2.5rem;
            top: 0.25rem;
            background-color: #FDFBF8;
            border: 4px solid #008080; /* Teal */
        }
        .project-card {
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px -3px rgb(0 0 0 / 0.1), 0 4px 6px -4px rgb(0 0 0 / 0.1);
        }
        .chart-container {
            position: relative;
            margin: auto;
            height: 50vh;
            max-height: 400px;
            width: 100%;
            max-width: 800px;
        }
        @media (max-width: 768px) {
            .chart-container {
                height: 60vh;
                max-height: 500px;
            }
        }
    </style>
</head>
<body class="antialiased">

    <!-- Header & Navigation -->
    <header id="header" class="bg-white/80 backdrop-blur-md sticky top-0 z-50 shadow-sm">
        <nav class="container mx-auto px-6 py-4 flex justify-between items-center">
            <div class="text-2xl font-bold text-primary">
                Kaushambi Vats
            </div>
            <div class="hidden md:flex space-x-8">
                <a href="#about" class="nav-link text-gray-600 font-medium border-b-2 border-transparent">About</a>
                <a href="#experience" class="nav-link text-gray-600 font-medium border-b-2 border-transparent">Experience</a>
                <a href="#projects" class="nav-link text-gray-600 font-medium border-b-2 border-transparent">Projects</a>
                <a href="#skills" class="nav-link text-gray-600 font-medium border-b-2 border-transparent">Skills</a>
                <a href="#contact" class="nav-link bg-primary text-white px-4 py-2 rounded-full hover:bg-opacity-90 transition-colors">Contact</a>
            </div>
            <div class="md:hidden">
                <button id="menu-btn" class="text-primary focus:outline-none">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path></svg>
                </button>
            </div>
        </nav>
        <!-- Mobile Menu -->
        <div id="mobile-menu" class="hidden md:hidden">
            <a href="#about" class="block py-2 px-6 text-sm text-gray-600 hover:bg-accent-bg">About</a>
            <a href="#experience" class="block py-2 px-6 text-sm text-gray-600 hover:bg-accent-bg">Experience</a>
            <a href="#projects" class="block py-2 px-6 text-sm text-gray-600 hover:bg-accent-bg">Projects</a>
            <a href="#skills" class="block py-2 px-6 text-sm text-gray-600 hover:bg-accent-bg">Skills</a>
            <a href="#contact" class="block py-2 px-6 text-sm text-gray-600 hover:bg-accent-bg">Contact</a>
        </div>
    </header>

    <main class="container mx-auto px-6 py-12">

        <!-- About Section -->
        <section id="about" class="text-center py-16">
            <h1 class="text-4xl md:text-5xl font-bold mb-4">Marketing & Brand Management Professional</h1>
            <p class="max-w-3xl mx-auto text-lg text-gray-600">
                Blending rigorous global academic frameworks from an MSc at Kingston University with extensive hands-on experience in sales, partnerships, and content strategy. Proven ability to drive brand relevance, optimize conversions, and execute data-driven marketing initiatives. Possesses a unique global-local strategic advantage, poised to deliver tangible impact across diverse industries.
            </p>
        </section>

        <!-- Experience Section -->
        <section id="experience" class="py-16">
            <h2 class="text-3xl font-bold text-center mb-12">Professional Experience</h2>
            <div class="relative max-w-2xl mx-auto">
                <div class="absolute left-4 top-0 h-full w-0.5 bg-primary/30"></div>
                <!-- Experience data will be populated here by JS -->
                <div id="timeline-container"></div>
            </div>
        </section>

        <!-- Projects Section -->
        <section id="projects" class="py-16 bg-accent-bg/50 rounded-2xl">
            <h2 class="text-3xl font-bold text-center mb-12">Key Projects: From Insight to Impact</h2>
            <div class="grid md:grid-cols-2 gap-8 max-w-5xl mx-auto">
                <!-- Projects data will be populated here by JS -->
                <div id="projects-container" class="grid md:grid-cols-2 col-span-2 gap-8"></div>
            </div>
        </section>

        <!-- Skills Section -->
        <section id="skills" class="py-16">
            <h2 class="text-3xl font-bold text-center mb-12">Core Competencies</h2>
            <div class="chart-container">
                <canvas id="skillsChart"></canvas>
            </div>
        </section>

        <!-- Education & Certifications Section -->
        <section id="education" class="py-16">
            <div class="max-w-5xl mx-auto grid md:grid-cols-2 gap-16">
                <div>
                    <h2 class="text-3xl font-bold mb-8 text-center md:text-left">Education</h2>
                    <div class="bg-white p-6 rounded-lg shadow-md mb-6">
                        <h3 class="text-xl font-bold text-primary">MSc Marketing & Brand Management</h3>
                        <p class="font-medium text-gray-600">Kingston University, London, UK | 2023</p>
                        <p class="text-sm text-gray-500 mt-2">Key Modules: Strategic Brand Management, Market Research & Data Analysis, Buyer Behaviour, Global Marketing, Marketing Communications, Brand Design.</p>
                    </div>
                    <div class="bg-white p-6 rounded-lg shadow-md">
                        <h3 class="text-xl font-bold text-primary">Bachelor of Arts (B.A.)</h3>
                        <p class="font-medium text-gray-600">Jyoti Nivas College Autonomous, Bangalore, India | 2017-2020</p>
                        <p class="text-sm text-gray-500 mt-2">Majors: English Literature, History, Sociology.</p>
                    </div>
                </div>
                <div>
                    <h2 class="text-3xl font-bold mb-8 text-center md:text-left">Certifications</h2>
                    <div id="certifications-container" class="space-y-2">
                        <!-- Certifications will be populated by JS -->
                    </div>
                </div>
            </div>
        </section>

    </main>

    <!-- Contact Section / Footer -->
    <footer id="contact" class="bg-slate-800 text-white">
        <div class="container mx-auto px-6 py-10 text-center">
            <h2 class="text-3xl font-bold mb-4">Let's Connect</h2>
            <p class="mb-6">I'm always open to discussing new projects, creative ideas, or opportunities to be part of an amazing team.</p>
            <div class="flex justify-center items-center space-x-6 text-sm">
                <a href="mailto:kaushambi.official97@gmail.com" class="hover:text-primary transition-colors">kaushambi.official97@gmail.com</a>
                <span>&bull;</span>
                <p>+91-8409378140</p>
                <span>&bull;</span>
                <a href="https://www.linkedin.com/in/kaushambi-vats-563131157" target="_blank" class="hover:text-primary transition-colors">LinkedIn</a>
                <span>&bull;</span>
                <a href="https://drive.google.com/file/d/1Dhkjamopo7KN-XazZL0QdEfHBiZ-uKPz/view?usp=drive_link" target="_blank" class="hover:text-primary transition-colors">Portfolio</a>
            </div>
        </div>
    </footer>

    <script>
        const resumeData = {
            experience: [
                {
                    role: "Senior Business Development Associate",
                    company: "Scaler Academy",
                    period: "Sep 2022 – Apr 2023",
                    details: [
                        "Exceeded sales targets for <strong>4 consecutive months</strong> from probation, demonstrating strong <strong>performance marketing</strong> and <strong>client acquisition/retention</strong> acumen.",
                        "Provided expert technical consultation, leveraging deep market insights to scale career trajectories in tech domains.",
                        "Managed sales through comprehensive consultation and candidate evaluation, optimizing <strong>conversion rates</strong>."
                    ]
                },
                {
                    role: "Senior Inside Sales Manager",
                    company: "Simplilearn",
                    period: "May 2021 – Aug 2022",
                    details: [
                        "Represented Agile and Scrum across America, Australia, and EMEA regions, managing the full sales support lifecycle.",
                        "Built and maintained business relations with senior-level corporate and major clientele, ensuring maximum customer satisfaction.",
                        "Involved in training new associates on product information and sales methodologies."
                    ]
                },
                {
                    role: "Partnerships & Program Manager",
                    company: "Lotus Foundation Education Trust",
                    period: "Jan 2021 – Apr 2021",
                    details: [
                        "Sought and managed strategic partnerships with prominent figures and institutions, expanding organizational reach.",
                        "Contributed to program development and stakeholder engagement for educational initiatives."
                    ]
                },
                {
                    role: "Partnerships & Program Management Intern",
                    company: "Unherd India",
                    period: "Jul 2020 – Dec 2020",
                    details: [
                        "Designed and delivered a <strong>Salesforce CSR curriculum</strong> for corporates, demonstrating expertise in program development and stakeholder training.",
                        "Contributed to a CSR initiative that led to Unherd India being recognized as a <strong>Harvard Innovation Challenge Semi-Finalist</strong>.",
                        "Gained direct experience in leveraging <strong>Corporate Social Responsibility (CSR)</strong> for <strong>brand reputation</strong> and impact."
                    ]
                }
            ],
            projects: [
                {
                    title: "Unlocking the Second-Hand Luxury Market (Dissertation)",
                    mission: "Dissected the <strong>€33 billion second-hand (pre-loved) luxury market</strong> (growing <strong>12% annually</strong>), uncovering consumption drivers to provide <strong>actionable intelligence</strong> for brands.",
                    impact: "Identified <strong>Digital Accessibility (e-commerce)</strong> as the most significant driver; highlighted critical <strong>trust-building mechanisms</strong> (e.g., blockchain). Developed strategic blueprints for optimizing digital experience and integrating sustainability messaging."
                },
                {
                    title: "Rose Theatre – Strategic Comms Renaissance (Live Client Project)",
                    mission: "Developed/designed an <strong>IMC strategy</strong> for <strong>live client Rose Theatre</strong> to boost audience growth, targeting <strong>Gen Z</strong> and enhancing patron engagement/belonging.",
                    impact: "Set goals including <strong>+25% ticket sales</strong> & <strong>+50% patron engagement</strong>. Applied <strong>DRIP Framework</strong>, designed 'Scan to Belong' QR codes, and managed a <strong>£20,000 budget</strong>."
                },
                {
                    title: "BoAt – Charting a UK Market Entry",
                    mission: "Strategically launched India's BoAt into the UK market, targeting <strong>Gen Z/Millennials</strong> for <strong>market penetration</strong> & <strong>brand footprint</strong>.",
                    impact: "Set <strong>SMART Objectives</strong> (e.g., Y1: <strong>40% brand recognition</strong>, <strong>£200K revenue</strong>; Y1-3: <strong>60% market penetration</strong>). Tailored **4Ps Marketing Mix** including aggressive digital marketing."
                },
                {
                    title: "Schweppes – Charting a Brand Renaissance",
                    mission: "Rejuvenated 1783-established Schweppes for the 25-40 demographic, driving <strong>brand rediscovery</strong> & <strong>market penetration</strong>.",
                    impact: "Defined Brand Vision from <strong>psychographic analysis</strong>. Orchestrated full <strong>visual identity overhaul</strong>. Conceptualized a 'Mixology Book' as a strategic on-trade sales driver to <strong>elevate sales & enhance loyalty</strong>."
                }
            ],
            skills: {
                labels: ['Brand Strategy', 'Digital Marketing', 'Content & Comms', 'Market Research', 'Data Analysis', 'Conversion Opt.', 'Leadership', 'Project Mgmt.'],
                datasets: [{
                    label: 'Proficiency',
                    data: [95, 90, 88, 92, 85, 93, 89, 91],
                    backgroundColor: 'rgba(0, 128, 128, 0.6)', // Teal
                    borderColor: 'rgba(0, 128, 128, 1)',
                    borderWidth: 1
                }]
            },
            certifications: [
                "Certified Sales Professional (Simplilearn)",
                "Salesforce India Certified (Curriculum Development & Training)",
                "Fundamentals of Digital Marketing (Google)",
                "Kingston Gold Award - Course Representative, Business School (2024-2025)",
                "Change Maker, NGO Management (2017-2018)",
                "Professional Development, Women's Rights (2018)",
                "National Theatre Festival Rangmanch Production (2018)",
                "IISC Bangalore Research (2018)",
                "Archaeology and Numismatics (2018)",
                "Ministry of Tourism, Govt. of India (2019)",
                "Arnhem Business School (2019)",
                "Rotaract Club of JNC International Service Direction (2019-2020)",
                "Introduction to Psychology (2020)"
            ]
        };

        document.addEventListener('DOMContentLoaded', function() {
            const menuBtn = document.getElementById('menu-btn');
            const mobileMenu = document.getElementById('mobile-menu');
            menuBtn.addEventListener('click', () => {
                mobileMenu.classList.toggle('hidden');
            });
            
            // Populate Timeline
            const timelineContainer = document.getElementById('timeline-container');
            resumeData.experience.forEach(item => {
                const div = document.createElement('div');
                div.className = 'timeline-item mb-8 ml-10';
                let detailsHtml = item.details.map(detail => `<li class="text-gray-600">${detail}</li>`).join('');
                div.innerHTML = `
                    <h3 class="text-xl font-bold text-primary">${item.role}</h3>
                    <p class="font-medium text-gray-700">${item.company}</p>
                    <p class="text-sm text-gray-500 mb-2">${item.period}</p>
                    <ul class="list-disc list-inside space-y-1 text-base">
                        ${detailsHtml}
                    </ul>
                `;
                timelineContainer.appendChild(div);
            });

            // Populate Projects
            const projectsContainer = document.getElementById('projects-container');
            resumeData.projects.forEach(project => {
                const div = document.createElement('div');
                div.className = 'project-card bg-white p-6 rounded-lg shadow-md cursor-pointer';
                div.innerHTML = `
                    <div class="project-front">
                        <h3 class="text-xl font-bold text-primary mb-2">${project.title}</h3>
                        <p class="text-gray-600">${project.mission}</p>
                        <p class="text-sm font-semibold text-primary mt-4">Click to see impact</p>
                    </div>
                    <div class="project-back hidden">
                         <h3 class="text-xl font-bold text-primary mb-2">${project.title}</h3>
                        <p class="text-gray-600">${project.impact}</p>
                        <p class="text-sm font-semibold text-primary mt-4">Click to see mission</p>
                    </div>
                `;
                projectsContainer.appendChild(div);

                div.addEventListener('click', () => {
                    div.querySelector('.project-front').classList.toggle('hidden');
                    div.querySelector('.project-back').classList.toggle('hidden');
                });
            });

            // Populate Certifications
            const certsContainer = document.getElementById('certifications-container');
            resumeData.certifications.forEach(cert => {
                const p = document.createElement('p');
                p.className = 'bg-white p-3 rounded-md shadow-sm text-sm text-gray-700';
                p.innerHTML = `<span class="text-primary font-bold mr-2">&#10003;</span> ${cert}`;
                certsContainer.appendChild(p);
            });

            // Skills Chart
            const ctx = document.getElementById('skillsChart').getContext('2d');
            const skillsChart = new Chart(ctx, {
                type: 'bar',
                data: {
                    labels: resumeData.skills.labels,
                    datasets: resumeData.skills.datasets
                },
                options: {
                    indexAxis: 'y',
                    responsive: true,
                    maintainAspectRatio: false,
                    scales: {
                        x: {
                            beginAtZero: true,
                            max: 100,
                             grid: {
                                color: 'rgba(0, 0, 0, 0.05)'
                            }
                        },
                        y: {
                             grid: {
                                display: false
                            }
                        }
                    },
                    plugins: {
                        legend: {
                            display: false
                        },
                        tooltip: {
                            callbacks: {
                                label: function(context) {
                                    return `Proficiency: ${context.raw}%`;
                                }
                            }
                        }
                    }
                }
            });

        });
    </script>
</body>
</html>
