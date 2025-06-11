<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Report: Herbal Cough Syrup Formulation</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Earthy Neutrals -->
    <!-- Application Structure Plan: A thematic, single-page narrative designed for exploration, aligning with the original report's content flow (intro, methodology, formulation, testing, conclusion). It starts with a comprehensive hero section (Introduction), transitions into interactive "Core Ingredients" cards, visualizes the "Formulation" percentages with a donut chart and a detailed list, explains the "Process" (Methodology) with an interactive step-by-step diagram, details "Quality & Safety" (Testing) in an accordion, and culminates in a dedicated "Conclusion" section. The PDF upload and viewing section has been removed as per user request. This structure transforms the linear report into an engaging story, prioritizing user understanding and interaction while maintaining a logical narrative progression. -->
    <!-- Visualization & Content Choices: Report sections are mapped to interactive goals. Introduction -> Inform (Enhanced Hero Text). Ingredients -> Inform -> Interactive HTML cards (JS reveal). Formulation % -> Compare Proportions -> Chart.js Donut Chart (hover interaction) and detailed HTML list. Methodology -> Explain Process -> HTML/CSS interactive timeline (JS click reveal). Testing -> Organize Info -> HTML/CSS/JS accordion. Conclusion -> Summarize -> Dedicated text section. This approach makes dense information accessible and engaging. -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #F8F7F4;
            color: #3D405B;
        }
        .chart-container {
            position: relative;
            margin: auto;
            height: 350px;
            width: 100%;
            max-width: 400px;
        }
        .step-content, .accordion-content {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.5s ease-in-out;
        }
        .active .step-content, .active .accordion-content {
            max-height: 500px;
        }
        .nav-link {
            transition: color 0.3s, border-bottom-color 0.3s;
        }
        .nav-link:hover, .nav-link.active {
            color: #D4A373;
            border-bottom-color: #D4A373;
        }
    </style>
</head>
<body class="antialiased">

    <header class="bg-white/80 backdrop-blur-md sticky top-0 z-50 shadow-sm">
        <nav class="container mx-auto px-6 py-4 flex justify-between items-center">
            <h1 class="text-xl font-bold text-[#3D405B]">Herbal Syrup Report</h1>
            <div class="hidden md:flex items-center space-x-8">
                <a href="#intro" class="nav-link text-gray-600 border-b-2 border-transparent">Introduction</a>
                <a href="#ingredients" class="nav-link text-gray-600 border-b-2 border-transparent">Ingredients</a>
                <a href="#formulation" class="nav-link text-gray-600 border-b-2 border-transparent">Formulation</a>
                <a href="#process" class="nav-link text-gray-600 border-b-2 border-transparent">Methodology</a>
                <a href="#testing" class="nav-link text-gray-600 border-b-2 border-transparent">Testing</a>
                <a href="#conclusion" class="nav-link text-gray-600 border-b-2 border-transparent">Conclusion</a>
            </div>
        </nav>
    </header>

    <main class="container mx-auto px-6 py-12">

        <section id="intro" class="text-center mb-20 scroll-mt-24">
            <h2 class="text-4xl md:text-5xl font-bold text-[#3D405B] mb-4">Unveiling Our Herbal Cough Syrup: An Interactive Journey</h2>
            <p class="max-w-3xl mx-auto text-lg text-gray-700 mb-8">
                This document invites you to delve into the intricate process behind our distinctive herbal cough syrup. Our core ambition? To present a genuinely natural, effective, and safe alternative to the conventional synthetic remedies prevalent today. It's increasingly evident that individuals are gravitating towards herbal solutions, drawn by their inherent naturalness, a reduced risk of adverse effects, and a heritage of centuries of trusted application. Historically, concoctions derived from medicinal plants have been a cornerstone for addressing common ailments such as coughs and colds. Our specific project thoughtfully combines a potent synergy of natural wonders: liquorice, dry ginger, *Pistacia integrimma*, *Ziziphus jujube*, and fig. Each of these has long been recognized for its capacity to alleviate throat irritation, quell inflammation, and soothe persistent coughs.
            </p>
            <p class="max-w-3xl mx-auto text-lg text-gray-700">
                The driving force behind this endeavor is a clear and growing public demand for gentle, yet powerful, options beyond typical cough syrups, which often include chemical additives and their associated unwanted consequences. We've crafted this interactive experience to ensure the scientific rigor underpinning our formulation is not only accessible but also truly engaging. Here, you'll discover the thoughtful reasoning behind our ingredient choices, comprehend the innovative methodology we've developed, observe the precise blueprint that brings it all to fruition, and explore the rigorous testing protocols that guarantee both its quality and your well-being.
            </p>
        </section>

        <section id="ingredients" class="mb-20 scroll-mt-24">
            <h3 class="text-3xl font-bold text-center mb-4 text-[#3D405B]">The Heart of the Remedy: Our Core Ingredients</h3>
            <p class="text-center max-w-2xl mx-auto text-gray-700 mb-12">
                The remarkable effectiveness of our syrup stems from a powerful blend of five extraordinary botanicals. Each plant boasts a rich legacy in traditional medicine, contributing a distinct spectrum of therapeutic properties. Their selection was no arbitrary decision; it emerged from meticulous research and extensive review of existing literature, specifically focusing on how each ingredient supports respiratory comfort and offers relief from coughs. We invite you to click on each card to uncover a deeper understanding of its individual contribution and the impressive health benefits it offers.
            </p>
            <div id="ingredients-grid" class="grid md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-5 gap-8">
            </div>
        </section>

        <section id="formulation" class="mb-20 scroll-mt-24">
            <h3 class="text-3xl font-bold text-center mb-4 text-[#3D405B]">Crafting the Blend: Our Formulation Blueprint</h3>
             <p class="text-center max-w-2xl mx-auto text-gray-700 mb-12">
                Achieving an effective and consistent herbal remedy hinges entirely on striking the perfect balance between its active components and foundational elements. This section, presented through an interactive chart and a comprehensive list, vividly illustrates the precise percentage of each ingredient incorporated into our final herbal cough syrup. This clear, quantitative breakdown not only reveals the exact proportions utilized but also emphasizes the critical role played by the base ingredients alongside our carefully measured herbal extracts. We encourage you to hover over the segments in the chart or consult the accompanying list for detailed information on the specific percentage contribution of every single component.
            </p>
            <div class="flex flex-col lg:flex-row items-center justify-center gap-8">
                <div class="w-full lg:w-1/2">
                    <div class="chart-container">
                        <canvas id="formulationChart"></canvas>
                    </div>
                </div>
                <div class="w-full lg:w-1/2">
                     <div class="bg-white p-6 rounded-lg shadow-md">
                        <h4 class="text-xl font-semibold mb-4 text-center">Ingredient Composition (by weight)</h4>
                        <ul id="formulation-list" class="space-y-2">
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <section id="process" class="mb-20 scroll-mt-24">
            <h3 class="text-3xl font-bold text-center mb-4 text-[#3D405B]">Our Unique Approach: The Infusion and Concentration Method</h3>
            <p class="text-center max-w-2xl mx-auto text-gray-700 mb-12">
                Our herbal cough syrup isn't merely a mixture; it's the product of our meticulously developed **Infusion and Concentration Method**. This bespoke approach was conceived with a singular objective: to extract the maximum beneficial compounds from our herbal ingredients while meticulously safeguarding their inherent healing properties. It's a precise, multi-stage journey that consistently produces a stable, highly effective syrup. We selected this method because it stands out in its ability to preserve potency, guarantee uniform distribution of all active components, and unfailingly deliver a high-quality product. Join us as we trace the transformation from raw herbs to our finished syrup by simply clicking on each step to reveal its detailed explanation!
            </p>
            <div id="process-steps" class="relative pl-8 border-l-2 border-dashed border-[#A3B18A]">
            </div>
        </section>

        <section id="testing" class="mb-20 scroll-mt-24">
            <h3 class="text-3xl font-bold text-center mb-4 text-[#3D405B]">Guaranteeing Excellence: Our Comprehensive Quality and Safety Protocols</h3>
             <p class="text-center max-w-2xl mx-auto text-gray-700 mb-12">
                Assuring the safety, stability, efficacy, and overall quality of our syrup is of utmost importance, a responsibility we approach with unwavering dedication. Consequently, we subject it to a series of stringent and exhaustive tests. These evaluations are absolutely fundamental for confirming that our product is not only entirely safe for consumption but also consistently delivers the therapeutic benefits you anticipate. Our testing regimen is comprehensive, encompassing everything from its fundamental physical and chemical attributes, to rigorous checks for microbiological purity, and detailed long-term stability assessments. We invite you to click on each category below to delve into the specific assessments we conduct and appreciate the significant role they play in upholding the exceptional standards of our herbal cough syrup.
            </p>
            <div id="testing-accordion" class="max-w-3xl mx-auto space-y-4">
            </div>
        </section>

        <section id="conclusion" class="mb-20 scroll-mt-24">
            <h3 class="text-3xl font-bold text-center mb-4 text-[#3D405B]">Concluding Thoughts</h3>
            <p class="max-w-3xl mx-auto text-lg text-gray-700 mb-8">
                To encapsulate, this report has guided you through the intricate development of our new herbal cough syrup. It's a thoughtfully conceived blend of nature's potent resources, including liquorice, dry ginger, *Pistacia integrimma*, *Ziziphus jujube*, and fig. At its core, this project is propelled by a commitment to address the escalating demand for natural, safe, and genuinely effective alternatives to conventional cough remedies, which, candidly, often come with undesirable side effects. Our distinctive **Infusion and Concentration Method** was specifically engineered to ensure the extraction and preservation of every beneficial compound, guaranteeing a product that is both reliable and highly potent.
            </p>
            <p class="max-w-3xl mx-auto text-lg text-gray-700 mb-8">
                We are confident that our formulated syrup will provide significant relief from coughs and throat irritation. It skillfully leverages the well-established anti-inflammatory, demulcent (soothing), and mucolytic (mucus-thinning) properties inherent in our carefully chosen herbs. Furthermore, the extensive **testing protocols** we've detailed — including physicochemical, microbiological, stability, and organoleptic evaluations — are not merely procedural. They are the bedrock that provides both us and you robust assurance of the syrup's quality, stability, and therapeutic effectiveness. This structured approach ensures that every facet of our product, from its raw components to its longevity, adheres to the most rigorous standards of safety and efficacy.
            </p>
            <p class="max-w-3xl mx-auto text-lg text-gray-700">
                Ultimately, we believe this herbal cough syrup represents a truly promising and secure option within the realm of natural healthcare. Its natural composition and deep roots in traditional medicinal practices position it as a compelling choice for anyone seeking gentle, yet powerful, relief from respiratory discomforts. Looking ahead, the indispensable next step involves conducting comprehensive preclinical and clinical trials. This will allow us to unequivocally confirm its efficacy, safety, and optimal dosage for human application, thereby paving the way for its widespread acceptance and beneficial integration into the broader market.
            </p>
        </section>

    </main>

    <footer class="bg-white mt-20">
        <div class="container mx-auto px-6 py-8 text-center text-gray-600">
            <p>&copy; 2025 Interactive Syrup Formulation Report. All data sourced from the original synopsis.</p>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {

            const ingredientsData = [
                { name: 'Liquorice', emoji: '🌿', scientific: 'Glycyrrhiza glabra', details: 'A cornerstone of this formulation, liquorice is renowned for its potent anti-inflammatory, antiviral, and mucolytic actions. It effectively soothes irritated throats by forming a protective film and assists in thinning and expelling mucus, thereby easing respiratory discomfort. Its historical application spans centuries across diverse traditional medicine systems for addressing various respiratory conditions.' },
                { name: 'Dry Ginger', emoji: '🌶️', scientific: 'Zingiber officinale', details: 'Dry ginger is a formidable natural agent, boasting robust anti-inflammatory, antioxidant, and antimicrobial qualities. Its inclusion is instrumental in significantly reducing the frequency and intensity of coughs, alleviating general respiratory discomfort, and bolstering the body\'s immune defenses against common pathogens. Furthermore, ginger\'s inherent warming properties offer additional comfort to the respiratory tract.' },
                { name: 'Pistacia', emoji: '🌳', scientific: 'Pistacia integrimma', details: 'Traditionally esteemed across various pharmacopoeias, Pistacia integrimma is predominantly employed for its ability to alleviate chest congestion and enhance overall respiratory function. Its recognized astringent and expectorant properties are believed to contribute to effective decongestion and provide notable relief from bronchial irritation, consequently facilitating easier breathing.' },
                { name: 'Ziziphus Jujube', emoji: '🍈', scientific: 'Ziziphus jujube', details: 'This remarkable fruit is highly regarded for its soothing and immune-boosting attributes. Ziziphus jujube is frequently integrated into traditional remedies to impart a calming effect on the throat, effectively assuage dry coughs and irritation, and promote restful sleep due to its gentle sedative characteristics, all of which contribute significantly to the overall recovery process.' },
                { name: 'Fig', emoji: '🍇', scientific: 'Ficus carica', details: 'Figs are broadly acknowledged for their demulcent and expectorant properties. They establish a protective, soothing layer over the mucous membranes lining the throat, thereby substantially mitigating discomfort and assisting in the expulsion of mucus. This beneficial action contributes to clearer airways and more effortless breathing.' }
            ];

            const formulationData = {
                labels: ['Sucrose', 'Liquorice', 'Dry Ginger', 'Pistacia', 'Ziziphus Jujube', 'Fig', 'Sal Ammoniac', 'Paprika Powder'],
                percentages: [89.19, 1.90, 1.90, 1.90, 1.90, 1.90, 0.78, 0.56],
                colors: ['#E0C4A4', '#A3B18A', '#B58DB6', '#F4A261', '#E76F51', '#D4A373', '#8CB369', '#E63946'],
            };
            
            const processData = [
                { step: 1, title: 'Herbal Infusion: The Gentle Extraction', details: 'All pre-weighed herbal ingredients—liquorice, dry ginger, Pistacia integrimma, Ziziphus jujube, and fig—are meticulously combined in a pristine vessel with 2 liters of potable water. This composite is then allowed to infuse undisturbed overnight, typically spanning 12 to 16 hours at ambient temperature. This extended immersion period is crucial for the methodical and gentle extraction of water-soluble active compounds from the botanical materials via a natural diffusion process, thereby ensuring maximal potency without compromise.' },
                { step: 2, title: 'Concentration: Intensifying the Extract', details: 'Following the infusion period, the herbal mixture is carefully transferred to a heating apparatus and gently warmed. The objective is to precisely reduce the water volume by half. This controlled concentration phase serves to enhance the density of the extracted active components, consequently elevating the therapeutic efficacy of the final syrup. Utmost caution is exercised to avert vigorous boiling, which could potentially induce thermal degradation of sensitive compounds.' },
                { step: 3, title: 'Filtration: Attaining Purity and Clarity', details: 'Upon achieving the desired volume reduction and allowing the mixture to slightly cool, the solution undergoes a meticulous filtration process. This entails an initial pass through a fine mesh sieve or cheesecloth to eliminate larger solid residues, followed by a thorough secondary filtration using specialized filter paper. This critical step ensures a limpid, uniform, and aesthetically appealing consistency in the final syrup, which concurrently enhances its palatability and overall quality.' },
                { step: 4, title: 'Syrup Formation: The Viscosity Milestone', details: 'The refined, filtered solution is subsequently returned to the heating apparatus and gently reheated. Sucrose, precisely 800g, is gradually incorporated while maintaining continuous agitation to facilitate its complete dissolution. Heating persists until the solution develops a characteristic syrup-like viscosity. This pivotal stage is scientifically validated by the "thread test," wherein a small aliquot of the solution, when drawn between two fingers, forms a delicate thread (typically observed at approximately 104°C or 220°F). This establishes the optimal consistency and sweetness for the syrup.' },
                { step: 5, title: 'Enhancement: Augmenting Therapeutic Properties', details: 'Immediately upon removing the syrup from the heat source, 7g of finely powdered Sal Ammoniac (ammonium chloride) is introduced. Sal Ammoniac is specifically included for its well-documented expectorant capabilities, which assist in the breakdown and expulsion of mucus, thereby amplifying the syrup\'s cough-alleviating effects. Concurrently, 5g of paprika powder is seamlessly integrated, serving as a natural colorant to bestow an appealing hue upon the syrup without necessitating artificial dyes.' },
                { step: 6, title: 'Homogenization: Ensuring Uniformity', details: 'Once all constituents have been added, the mixture undergoes thorough stirring utilizing a sterilized rod or whisk until complete uniformity is achieved. This crucial procedural step guarantees that both the Sal Ammoniac and paprika powder are evenly dispersed throughout the syrup, and that all active compounds are consistently distributed. Such meticulous blending maintains the product\'s integrity and ensures reliable dosing and efficacy with each administration.' },
                { step: 7, title: 'Cooling & Bottling: Preservation and Storage', details: 'The prepared syrup is allowed to cool naturally to ambient temperature within a controlled environment. Subsequently, it is aseptically transferred into pre-sterilized glass bottles. Immediate and tight sealing of the bottles post-filling is imperative for upholding optimal hygiene, preventing any microbial contamination, and significantly extending the shelf life of the herbal cough syrup, thereby ensuring its sustained safety and effectiveness over time.' }
            ];
            
            const testingData = [
                { category: 'Physicochemical Evaluation', icon: '⚖️', details: 'These essential tests meticulously assess the fundamental physical and chemical attributes of the syrup. This battery includes **pH Measurement**, critical for influencing stability, solubility, and the biological availability of active ingredients, alongside impacting palatability and potential throat irritation. **Viscosity Determination** is performed to ascertain optimal flow characteristics and effective adherence to the throat, contributing to its soothing action. **Specific Gravity** offers a reliable indicator of the dissolved solids concentration, vital for ensuring batch-to-batch consistency. Lastly, **Refractive Index** serves as a robust quality control check for sugar concentration and the overall purity profile of the syrup.' },
                { category: 'Microbiological Purity', icon: '🔬', details: 'These rigorous analyses are conducted to unequivocally verify that the product is entirely free from deleterious microorganisms and adheres to stringent safety regulations. They encompass the **Total Viable Aerobic Count (TVAC)**, which quantifies all living aerobic bacteria; the **Total Yeast and Mold Count (TYMC)**, specifically identifying prevalent spoilage fungi; and crucial examinations for the **Absence of Specific Pathogens** such as *Escherichia coli*, *Salmonella spp.*, and *Staphylococcus aureus*, all of which are indispensable for safeguarding consumer health.' },
                { category: 'Stability Studies', icon: '⏳', details: 'These investigations are paramount for establishing the prospective shelf life and long-term integrity of the product. **Accelerated Stability Studies** entail storing the syrup under deliberately intensified stress conditions (e.g., elevated temperatures like 40°C ± 2°C and heightened humidity) for compressed durations to prognosticate its extended stability. Concurrently, **Real-Time Stability Studies** involve continuous monitoring of the syrup under recommended storage parameters (e.g., ambient temperature 25°C ± 2°C) throughout its entire proposed shelf life, with periodic assays performed to definitively confirm its actual stability and effectiveness over time.' },
                { category: 'Organoleptic Properties', icon: '👃', details: 'These evaluations appraise the sensory characteristics of the syrup, which are pivotal for fostering patient acceptance and adherence. **Appearance** involves a thorough visual inspection for clarity, uniform coloration, and the absence of any undesirable precipitates. **Odor** is assessed for the distinctive herbal aroma and to detect any atypical or "off-notes" that might signal spoilage. **Taste** is meticulously evaluated by a trained panel for optimal sweetness, balanced herbal undertones, and the complete absence of bitterness or unpleasant aftertastes, ensuring the syrup offers a pleasant consumption experience.' }
            ];

            const ingredientsGrid = document.getElementById('ingredients-grid');
            ingredientsData.forEach(ing => {
                const card = document.createElement('div');
                card.className = 'ingredient-card bg-white p-6 rounded-lg shadow-md cursor-pointer transform hover:-translate-y-1 transition-transform duration-300';
                card.innerHTML = `
                    <div class="text-4xl mb-4">${ing.emoji}</div>
                    <h4 class="text-xl font-bold mb-2">${ing.name}</h4>
                    <p class="text-sm text-gray-500 italic mb-4">${ing.scientific}</p>
                    <div class="details text-gray-700 hidden">
                        <p>${ing.details}</p>
                    </div>
                `;
                ingredientsGrid.appendChild(card);

                card.addEventListener('click', () => {
                    const details = card.querySelector('.details');
                    details.classList.toggle('hidden');
                    card.classList.toggle('ring-2');
                    card.classList.toggle('ring-[#D4A373]');
                });
            });

            const formulationList = document.getElementById('formulation-list');
            formulationData.labels.forEach((label, i) => {
                const listItem = document.createElement('li');
                listItem.className = 'flex justify-between items-center text-gray-700';
                listItem.innerHTML = `
                    <span>
                        <span class="inline-block w-3 h-3 rounded-full mr-2" style="background-color: ${formulationData.colors[i]}"></span>
                        ${label}
                    </span>
                    <span class="font-semibold">${formulationData.percentages[i]}%</span>
                `;
                formulationList.appendChild(listItem);
            });
            
            const ctx = document.getElementById('formulationChart').getContext('2d');
            new Chart(ctx, {
                type: 'doughnut',
                data: {
                    labels: formulationData.labels,
                    datasets: [{
                        data: formulationData.percentages,
                        backgroundColor: formulationData.colors,
                        borderColor: '#F8F7F4',
                        borderWidth: 3,
                        hoverOffset: 15
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: {
                            display: false
                        },
                        tooltip: {
                            callbacks: {
                                label: function(context) {
                                    let label = context.label || '';
                                    if (label) {
                                        label += ': ';
                                    }
                                    if (context.parsed !== null) {
                                        label += context.parsed + '%';
                                    }
                                    return label;
                                }
                            }
                        }
                    },
                    cutout: '60%'
                }
            });

            const processStepsContainer = document.getElementById('process-steps');
            processData.forEach(item => {
                const stepEl = document.createElement('div');
                stepEl.className = 'mb-10 step-item';
                stepEl.innerHTML = `
                    <div class="flex items-center mb-1 cursor-pointer step-header">
                        <div class="absolute -left-4 bg-[#A3B18A] text-white rounded-full h-8 w-8 flex items-center justify-center font-bold">
                            ${item.step}
                        </div>
                        <h4 class="font-bold text-xl ml-8 text-[#3D405B]">${item.title}</h4>
                    </div>
                    <div class="ml-8 step-content">
                        <p class="text-gray-600">${item.details}</p>
                    </div>
                `;
                processStepsContainer.appendChild(stepEl);

                stepEl.querySelector('.step-header').addEventListener('click', () => {
                    stepEl.classList.toggle('active');
                });
            });

            const testingAccordionContainer = document.getElementById('testing-accordion');
            testingData.forEach(item => {
                const accEl = document.createElement('div');
                accEl.className = 'bg-white rounded-lg shadow-md overflow-hidden accordion-item';
                accEl.innerHTML = `
                    <div class="p-4 flex justify-between items-center cursor-pointer accordion-header">
                        <h4 class="font-semibold text-lg flex items-center">
                            <span class="mr-3">${item.icon}</span>
                            ${item.category}
                        </h4>
                        <span class="transform transition-transform duration-300 text-2xl font-thin text-gray-500">+</span>
                    </div>
                    <div class="accordion-content">
                        <p class="px-4 pb-4 text-gray-600">${item.details}</p>
                    </div>
                `;
                testingAccordionContainer.appendChild(accEl);

                accEl.querySelector('.accordion-header').addEventListener('click', () => {
                    accEl.classList.toggle('active');
                    const icon = accEl.querySelector('.accordion-header span:last-child');
                    if (accEl.classList.contains('active')) {
                        icon.style.transform = 'rotate(45deg)';
                    } else {
                        icon.style.transform = 'rotate(0deg)';
                    }
                });
            });

            const navLinks = document.querySelectorAll('.nav-link');
            const sections = document.querySelectorAll('section');

            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        navLinks.forEach(link => {
                            link.classList.remove('active');
                            if (link.getAttribute('href').substring(1) === entry.target.id) {
                                link.classList.add('active');
                            }
                        });
                    }
                });
            }, { rootMargin: '-30% 0px -70% 0px' });

            sections.forEach(section => {
                observer.observe(section);
            });
            
            navLinks.forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    document.querySelector(this.getAttribute('href')).scrollIntoView({
                        behavior: 'smooth'
                    });
                });
            });
        });
    </script>

</body>
</html>
