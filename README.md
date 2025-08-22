<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Formation SADASSUR | Assurance Emprunteur</title>
    <!-- Font 'Inter' pour une typographie moderne -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <!-- Tailwind CSS pour un design rapide et responsive -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Chart.js pour les graphiques interactifs -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <!-- Font Awesome pour les icônes visuelles -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f3f4f6; /* Fond léger */
        }
        /* Styles pour les sections repliables avec transition */
        .module-content {
            transition: max-height 0.5s ease-in-out, opacity 0.5s ease-in-out;
            max-height: 0;
            overflow: hidden;
            opacity: 0;
        }
        .module-content.active {
            max-height: 2000px; /* Grande valeur pour permettre l'expansion */
            opacity: 1;
        }
        .module-header {
            cursor: pointer;
            user-select: none;
            transition: background-color 0.3s ease-in-out;
        }
        .module-header:hover {
            background-color: rgba(255, 255, 255, 0.2);
        }
        .rotate-180 {
            transform: rotate(180deg);
            transition: transform 0.3s ease-in-out;
        }
        /* Style pour les bulles de chat */
        .chat-bubble {
            max-width: 80%;
            padding: 1rem;
            border-radius: 1.5rem;
        }
        .chat-bubble-user {
            background-color: #0d9488;
            color: white;
            border-bottom-right-radius: 0;
            align-self: flex-end;
        }
        .chat-bubble-customer {
            background-color: #e5e7eb;
            color: #1f2937;
            border-bottom-left-radius: 0;
            align-self: flex-start;
        }
        .correct-answer-label {
            color: #16a34a;
            font-weight: bold;
        }
        .incorrect-answer-label {
            color: #dc2626;
            font-weight: bold;
        }
        /* Couleurs pour les modules pour un code visuel */
        .module-color-0 { --module-color: #3f88c5; } /* Bleu */
        .module-color-1 { --module-color: #f59e0b; } /* Jaune */
        .module-color-2 { --module-color: #22c55e; } /* Vert */
        .module-color-3 { --module-color: #ef4444; } /* Rouge */
        .module-color-4 { --module-color: #3b82f6; } /* Bleu clair */
        .module-color-5 { --module-color: #8b5cf6; } /* Violet */
        .module-color-6 { --module-color: #ec4899; } /* Rose */
        .module-color-7 { --module-color: #06b6d4; } /* Cyan */
        .module-color-8 { --module-color: #3d5a80; } /* Gris bleu */
        .module-color-9 { --module-color: #2a9d8f; } /* Vert d'eau */

        .toc-link.active {
            font-weight: bold;
            color: var(--module-color);
            background-color: #1f2937;
        }
        .toc-link {
            transition: all 0.2s ease-in-out;
        }
        .toc-link:hover {
            transform: translateX(5px);
        }

        /* Style pour le certificat sur canvas */
        .certificate-container {
            display: flex;
            justify-content: center;
            align-items: center;
        }
        #certificateCanvas {
            border: 2px solid #06b6d4;
            background-color: #ffffff;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
    </style>
</head>

<body class="bg-gray-100 flex flex-col min-h-screen text-gray-800">

    <!-- Titre et en-tête de la formation -->
    <header class="bg-gradient-to-r from-teal-700 to-blue-800 text-white shadow-lg py-6 px-6 md:px-12 sticky top-0 z-50">
        <h1 class="text-xl md:text-3xl font-bold text-center">Formation SADASSUR | Assurance Emprunteur</h1>
        <p class="text-center mt-2 text-sm italic">Maîtriser les fondamentaux pour exceller</p>
    </header>

    <!-- Conteneur principal de la page -->
    <div class="flex flex-col md:flex-row flex-1 pt-6">

        <!-- Table des matières (Menu de navigation latéral) -->
        <nav class="md:w-64 bg-gray-900 text-white p-6 md:sticky top-20 md:h-[calc(100vh-5rem)] overflow-y-auto shadow-xl z-40 rounded-r-lg">
            <h2 class="text-2xl font-bold mb-4">Plan de la Formation</h2>
            <ul class="space-y-2">
                <li>
                    <a href="#module-1" class="toc-link block py-3 px-4 rounded-lg hover:bg-gray-700 transition-colors duration-200" style="color: #3f88c5;">
                        <i class="fas fa-building mr-2 w-6 text-center"></i> Présentation de SADASSUR
                    </a>
                </li>
                <li>
                    <a href="#module-2" class="toc-link block py-3 px-4 rounded-lg hover:bg-gray-700 transition-colors duration-200" style="color: #f59e0b;">
                        <i class="fas fa-handshake mr-2 w-6 text-center"></i> Fondamentaux de l'AE
                    </a>
                </li>
                <li>
                    <a href="#module-3" class="toc-link block py-3 px-4 rounded-lg hover:bg-gray-700 transition-colors duration-200" style="color: #22c55e;">
                        <i class="fas fa-gavel mr-2 w-6 text-center"></i> Cadre Réglementaire
                    </a>
                </li>
                <li>
                    <a href="#module-4" class="toc-link block py-3 px-4 rounded-lg hover:bg-gray-700 transition-colors duration-200" style="color: #ef4444;">
                        <i class="fas fa-bullseye mr-2 w-6 text-center"></i> Techniques de Vente
                    </a>
                </li>
                <li>
                    <a href="#module-5" class="toc-link block py-3 px-4 rounded-lg hover:bg-gray-700 transition-colors duration-200" style="color: #3b82f6;">
                        <i class="fas fa-shield-alt mr-2 w-6 text-center"></i> Traitement des Objections
                    </a>
                </li>
                <li>
                    <a href="#module-6" class="toc-link block py-3 px-4 rounded-lg hover:bg-gray-700 transition-colors duration-200" style="color: #8b5cf6;">
                        <i class="fas fa-smile-beam mr-2 w-6 text-center"></i> Satisfaction Clientèle
                    </a>
                </li>
                <li>
                    <a href="#module-7" class="toc-link block py-3 px-4 rounded-lg hover:bg-gray-700 transition-colors duration-200" style="color: #ec4899;">
                        <i class="fas fa-microphone mr-2 w-6 text-center"></i> Communication Efficace
                    </a>
                </li>
                <li>
                    <a href="#module-8" class="toc-link block py-3 px-4 rounded-lg hover:bg-gray-700 transition-colors duration-200" style="color: #06b6d4;">
                        <i class="fas fa-chart-line mr-2 w-6 text-center"></i> Simulateurs & Outils
                    </a>
                </li>
                <li>
                    <a href="#module-9" class="toc-link block py-3 px-4 rounded-lg hover:bg-gray-700 transition-colors duration-200" style="color: #3d5a80;">
                        <i class="fas fa-user-friends mr-2 w-6 text-center"></i> Études de Cas
                    </a>
                </li>
                <li>
                    <a href="#module-10" class="toc-link block py-3 px-4 rounded-lg hover:bg-gray-700 transition-colors duration-200" style="color: #2a9d8f;">
                        <i class="fas fa-book-reader mr-2 w-6 text-center"></i> Glossaire & Quiz Final
                    </a>
                </li>
            </ul>
        </nav>

        <!-- Contenu principal -->
        <main class="flex-1 p-6 md:p-12 space-y-8">
            <div class="space-y-8 max-w-4xl mx-auto">
                
                <!-- Chaque section est une carte visuelle -->
                <section id="module-1" class="bg-white rounded-xl shadow-lg overflow-hidden module-color-0 border-l-8 border-blue-600">
                    <div class="module-header p-6 flex justify-between items-center bg-blue-100/30">
                        <h2 class="text-2xl font-bold flex items-center text-blue-800">
                            <i class="fas fa-building text-blue-600 mr-4"></i> Module 1 : Présentation de SADASSUR
                        </h2>
                        <i class="fas fa-chevron-down text-blue-600 toggle-icon transition-transform duration-300"></i>
                    </div>
                    <div class="module-content active p-6 text-gray-700">
                        <h3 class="text-xl font-semibold mb-4 text-blue-600">Notre mission</h3>
                        <p class="mb-4">
                            SADASSUR est un cabinet de courtage en assurances spécialisé dans la délégation d'assurance emprunteur. Notre mission est d'accompagner nos clients dans la recherche et la souscription d'une assurance de prêt optimale, en leur garantissant les meilleures conditions du marché et une protection sur mesure.
                        </p>
                        
                        <h3 class="text-xl font-semibold mb-4 text-blue-600">Nos valeurs</h3>
                        <ul class="list-disc list-inside space-y-2 mb-6">
                            <li><strong>Expertise :</strong> Une connaissance approfondie du marché pour conseiller au mieux nos clients.</li>
                            <li><strong>Transparence :</strong> Des explications claires et un suivi personnalisé à chaque étape.</li>
                            <li><strong>Proximité :</strong> Un interlocuteur unique et disponible pour répondre à toutes les questions.</li>
                        </ul>
                    </div>
                </section>

                <section id="module-2" class="bg-white rounded-xl shadow-lg overflow-hidden module-color-1 border-l-8 border-yellow-500">
                    <div class="module-header p-6 flex justify-between items-center bg-yellow-100/30">
                        <h2 class="text-2xl font-bold flex items-center text-yellow-600">
                            <i class="fas fa-handshake text-yellow-600 mr-4"></i> Module 2 : Les Fondamentaux de l'Assurance Emprunteur
                        </h2>
                        <i class="fas fa-chevron-down text-yellow-600 toggle-icon transition-transform duration-300"></i>
                    </div>
                    <div class="module-content p-6 text-gray-700">
                        <h3 class="text-xl font-semibold mb-4 text-yellow-600">Qu'est-ce que l'assurance emprunteur ?</h3>
                        <p class="mb-4">
                            L'assurance emprunteur est une assurance qui garantit le remboursement de votre prêt immobilier ou de votre crédit à la consommation en cas de survenance de certains événements imprévus qui vous empêcheraient de payer vos mensualités. C'est une sécurité financière aussi bien pour vous que pour l'établissement de crédit.
                        </p>
                        <p class="mb-4 font-semibold">
                            C'est l'un des piliers de la négociation d'un prêt et un élément essentiel de la protection du patrimoine familial.
                        </p>

                        <h3 class="text-xl font-semibold mb-4 text-yellow-600">Les Garanties Clés</h3>
                        <p class="mb-4">Voici les principales garanties que l'on trouve dans un contrat d'assurance emprunteur. Chaque garantie offre une protection spécifique.</p>
                        <ul class="list-none space-y-4 mb-6">
                            <li class="p-4 bg-gray-50 rounded-lg shadow-sm border-l-4 border-yellow-400">
                                <h4 class="font-bold text-lg text-yellow-600">Décès et Perte Totale et Irréversible d'Autonomie (PTIA)</h4>
                                <p class="mt-2">
                                    Cette garantie est la plus importante et souvent obligatoire. Elle se déclenche en cas de décès de l'emprunteur ou si celui-ci devient incapable d'exercer toute activité rémunérée et a besoin de l'assistance d'une tierce personne pour les actes de la vie courante.
                                </p>
                            </li>
                            <li class="p-4 bg-gray-50 rounded-lg shadow-sm border-l-4 border-yellow-400">
                                <h4 class="font-bold text-lg text-yellow-600">Invalidité Permanente Totale (IPT) et Partielle (IPP)</h4>
                                <p class="mt-2">
                                    Ces garanties s'activent si l'emprunteur subit une invalidité consécutive à une maladie ou un accident, réduisant sa capacité de travail de manière permanente. L'IPT couvre une invalidité de plus de 66%, tandis que l'IPP couvre une invalidité entre 33% et 66%.
                                </p>
                            </li>
                            <li class="p-4 bg-gray-50 rounded-lg shadow-sm border-l-4 border-yellow-400">
                                <h4 class="font-bold text-lg text-yellow-600">Incapacité Temporaire Totale (ITT) de travail</h4>
                                <p class="mt-2">
                                    Cette garantie prend le relais pendant une période d'arrêt de travail temporaire, consécutive à une maladie ou un accident, qui vous empêche d'exercer votre profession.
                                </p>
                            </li>
                            <li class="p-4 bg-gray-50 rounded-lg shadow-sm border-l-4 border-yellow-400">
                                <h4 class="font-bold text-lg text-yellow-600">Garantie Perte d'Emploi</h4>
                                <p class="mt-2">
                                    Souvent facultative, elle offre une protection en cas de licenciement. Elle prend en charge tout ou partie des mensualités pendant une période définie par le contrat, le temps que l'emprunteur retrouve un emploi.
                                </p>
                            </li>
                        </ul>
                    </div>
                </section>
                
                <section id="module-3" class="bg-white rounded-xl shadow-lg overflow-hidden module-color-2 border-l-8 border-green-500">
                    <div class="module-header p-6 flex justify-between items-center bg-green-100/30">
                        <h2 class="text-2xl font-bold flex items-center text-green-600">
                            <i class="fas fa-gavel text-green-600 mr-4"></i> Module 3 : Cadre Réglementaire et Légal
                        </h2>
                        <i class="fas fa-chevron-down text-green-600 toggle-icon transition-transform duration-300"></i>
                    </div>
                    <div class="module-content p-6 text-gray-700">
                        <h3 class="text-xl font-semibold mb-4 text-green-600">Les principales lois et conventions</h3>
                        <p class="mb-4">
                            Maîtriser le cadre légal est essentiel pour conseiller au mieux vos clients et les rassurer sur leurs droits.
                        </p>
                        <ul class="list-none space-y-4 mb-6">
                            <li class="p-4 bg-gray-50 rounded-lg shadow-sm border-l-4 border-green-400">
                                <h4 class="font-bold text-lg text-green-600">Loi Lagarde (2010)</h4>
                                <p class="mt-2">
                                    Elle a introduit le "libre choix" de l'assurance emprunteur. Les banques ne peuvent plus imposer leur propre contrat d'assurance.
                                </p>
                            </li>
                            <li class="p-4 bg-gray-50 rounded-lg shadow-sm border-l-4 border-green-400">
                                <h4 class="font-bold text-lg text-green-600">Loi Hamon (2014) et Amendement Bourquin (2018)</h4>
                                <p class="mt-2">
                                    Ces lois permettent la résiliation annuelle du contrat d'assurance de prêt.
                                </p>
                            </li>
                            <li class="p-4 bg-gray-50 rounded-lg shadow-sm border-l-4 border-green-400">
                                <h4 class="font-bold text-lg text-green-600">Loi Lemoine (2022)</h4>
                                <p class="mt-2">
                                    La loi la plus récente, elle permet la résiliation de l'assurance emprunteur à tout moment, sans frais.
                                </p>
                            </li>
                            <li class="p-4 bg-gray-50 rounded-lg shadow-sm border-l-4 border-green-400">
                                <h4 class="font-bold text-lg text-green-600">Convention AERAS</h4>
                                <p class="mt-2">
                                    Facilite l'accès à l'assurance de prêt pour les personnes présentant un risque de santé aggravé.
                                </p>
                            </li>
                        </ul>
                    </div>
                </section>

                <section id="module-4" class="bg-white rounded-xl shadow-lg overflow-hidden module-color-3 border-l-8 border-red-500">
                    <div class="module-header p-6 flex justify-between items-center bg-red-100/30">
                        <h2 class="text-2xl font-bold flex items-center text-red-600">
                            <i class="fas fa-bullseye text-red-600 mr-4"></i> Module 4 : Techniques de Vente & d'Accroche
                        </h2>
                        <i class="fas fa-chevron-down text-red-600 toggle-icon transition-transform duration-300"></i>
                    </div>
                    <div class="module-content p-6 text-gray-700">
                        <h3 class="text-xl font-semibold mb-4 text-red-600">La Méthode A.I.D.A</h3>
                        <p class="mb-4">
                            La méthode A.I.D.A. (Attention, Intérêt, Désir, Action) est une approche classique mais toujours efficace pour structurer un entretien de vente.
                        </p>
                        <h3 class="text-xl font-semibold mb-4 text-red-600">Quizz Rapide</h3>
                        <div class="quiz space-y-4">
                            <p class="font-semibold">Quelle est la première étape de la méthode A.I.D.A. ?</p>
                            <div class="flex items-center space-x-2">
                                <input type="radio" id="q1a" name="q1" value="Attention" class="radio-button">
                                <label for="q1a">Attention</label>
                            </div>
                            <div class="flex items-center space-x-2">
                                <input type="radio" id="q1b" name="q1" value="Intérêt" class="radio-button">
                                <label for="q1b">Intérêt</label>
                            </div>
                            <button onclick="checkAnswer('q1', 'Attention', event)" class="mt-2 py-2 px-4 bg-red-600 text-white rounded-md shadow-md hover:bg-red-700 transition-colors">Vérifier</button>
                            <div id="result-q1" class="mt-2"></div>
                        </div>
                    </div>
                </section>
                
                <section id="module-5" class="bg-white rounded-xl shadow-lg overflow-hidden module-color-4 border-l-8 border-blue-500">
                    <div class="module-header p-6 flex justify-between items-center bg-blue-100/30">
                        <h2 class="text-2xl font-bold flex items-center text-blue-600">
                            <i class="fas fa-shield-alt text-blue-600 mr-4"></i> Module 5 : Traitement des Objections
                        </h2>
                        <i class="fas fa-chevron-down text-blue-600 toggle-icon transition-transform duration-300"></i>
                    </div>
                    <div class="module-content p-6 text-gray-700">
                        <h3 class="text-xl font-semibold mb-4 text-blue-600">Les 4 étapes pour surmonter une objection</h3>
                        <p class="mb-4">
                            Les objections ne sont pas des refus, mais des signaux d'intérêt. Les gérer avec méthode est essentiel.
                        </p>
                        <ul class="list-decimal list-inside space-y-2 mb-6">
                            <li><strong>Écouter :</strong> Laissez le client s'exprimer pleinement sans l'interrompre.</li>
                            <li><strong>Reformuler :</strong> Validez votre compréhension de l'objection.</li>
                            <li><strong>Isoler :</strong> Assurez-vous qu'il s'agit de la seule objection principale.</li>
                            <li><strong>Répondre :</strong> Apportez une réponse pertinente et rassurante.</li>
                        </ul>
                    </div>
                </section>
                
                <section id="module-6" class="bg-white rounded-xl shadow-lg overflow-hidden module-color-5 border-l-8 border-purple-500">
                    <div class="module-header p-6 flex justify-between items-center bg-purple-100/30">
                        <h2 class="text-2xl font-bold flex items-center text-purple-600">
                            <i class="fas fa-smile-beam text-purple-600 mr-4"></i> Module 6 : Satisfaction Clientèle
                        </h2>
                        <i class="fas fa-chevron-down text-purple-600 toggle-icon transition-transform duration-300"></i>
                    </div>
                    <div class="module-content p-6 text-gray-700">
                        <h3 class="text-xl font-semibold mb-4 text-purple-600">Pourquoi la satisfaction est-elle cruciale ?</h3>
                        <p class="mb-4">
                            Un client satisfait est un client fidèle et un ambassadeur de la marque.
                        </p>
                    </div>
                </section>
                
                <section id="module-7" class="bg-white rounded-xl shadow-lg overflow-hidden module-color-6 border-l-8 border-pink-500">
                    <div class="module-header p-6 flex justify-between items-center bg-pink-100/30">
                        <h2 class="text-2xl font-bold flex items-center text-pink-600">
                            <i class="fas fa-microphone text-pink-600 mr-4"></i> Module 7 : Communication Efficace
                        </h2>
                        <i class="fas fa-chevron-down text-pink-600 toggle-icon transition-transform duration-300"></i>
                    </div>
                    <div class="module-content p-6 text-gray-700">
                        <h3 class="text-xl font-semibold mb-4 text-pink-600">Écoute Active et Empathie</h3>
                        <p class="mb-4">
                            La communication est au cœur de votre métier. L'écoute active consiste à écouter attentivement le client, sans jugement.
                        </p>
                        <div class="simulation p-4 bg-gray-100 rounded-lg shadow-inner flex flex-col space-y-4">
                            <div class="chat-bubble chat-bubble-customer">
                                "Je trouve que votre prix est trop élevé. Je ne suis pas sûr de vouloir continuer."
                            </div>
                            <div class="chat-bubble chat-bubble-user">
                                "Je comprends votre point de vue sur le prix. Vous avez l'impression que le coût est un frein pour vous, c'est bien cela ?"
                            </div>
                        </div>
                    </div>
                </section>

                <section id="module-8" class="bg-white rounded-xl shadow-lg overflow-hidden module-color-7 border-l-8 border-cyan-500">
                    <div class="module-header p-6 flex justify-between items-center bg-cyan-100/30">
                        <h2 class="text-2xl font-bold flex items-center text-cyan-600">
                            <i class="fas fa-chart-line text-cyan-600 mr-4"></i> Module 8 : Simulateurs & Outils
                        </h2>
                        <i class="fas fa-chevron-down text-cyan-600 toggle-icon transition-transform duration-300"></i>
                    </div>
                    <div class="module-content p-6 text-gray-700">
                        <h3 class="text-xl font-semibold mb-4 text-cyan-600">Visualisation des économies</h3>
                        <p class="mb-4">
                            Utilisez cet outil pour montrer les économies potentielles en changeant d'assurance emprunteur.
                        </p>
                        <div class="space-y-4 max-w-lg mx-auto p-4 bg-gray-50 rounded-lg shadow-inner">
                            <div class="flex items-center space-x-2">
                                <label for="initial-rate" class="w-1/2">Taux initial (%) :</label>
                                <input type="number" id="initial-rate" value="0.30" step="0.01" class="w-1/2 p-2 rounded-md border border-gray-300">
                            </div>
                            <div class="flex items-center space-x-2">
                                <label for="sadassur-rate" class="w-1/2">Taux SADASSUR (%) :</label>
                                <input type="number" id="sadassur-rate" value="0.15" step="0.01" class="w-1/2 p-2 rounded-md border border-gray-300">
                            </div>
                            <div class="flex items-center space-x-2">
                                <label for="loan-amount" class="w-1/2">Montant du prêt (€) :</label>
                                <input type="number" id="loan-amount" value="250000" class="w-1/2 p-2 rounded-md border border-gray-300">
                            </div>
                            <div class="flex items-center space-x-2">
                                <label for="duration" class="w-1/2">Durée (ans) :</label>
                                <input type="number" id="duration" value="20" class="w-1/2 p-2 rounded-md border border-gray-300">
                            </div>
                            <button id="calculate-btn" class="w-full py-2 px-4 bg-cyan-600 text-white rounded-md shadow-md hover:bg-cyan-700 transition-colors">Calculer les économies</button>
                        </div>
                        <div class="mt-8">
                            <h4 class="text-lg font-semibold mb-2 text-center text-cyan-600">Répartition des primes d'assurance</h4>
                            <div class="flex justify-center">
                                <canvas id="sadassurChart" class="max-w-md"></canvas>
                            </div>
                        </div>
                    </div>
                </section>

                <section id="module-9" class="bg-white rounded-xl shadow-lg overflow-hidden module-color-8 border-l-8 border-gray-600">
                    <div class="module-header p-6 flex justify-between items-center bg-gray-200/50">
                        <h2 class="text-2xl font-bold flex items-center text-gray-700">
                            <i class="fas fa-user-friends text-gray-700 mr-4"></i> Module 9 : Études de Cas Pratiques
                        </h2>
                        <i class="fas fa-chevron-down text-gray-700 toggle-icon transition-transform duration-300"></i>
                    </div>
                    <div class="module-content p-6 text-gray-700">
                        <h3 class="text-xl font-semibold mb-4 text-gray-700">Cas Pratique #1 : Le client avec des risques de santé</h3>
                        <p class="mb-4">
                            M. Martin, 45 ans, est un ancien fumeur et a récemment été traité pour une hypertension.
                        </p>
                        <h3 class="text-xl font-semibold mb-4 text-gray-700">Cas Pratique #2 : Le jeune couple primo-accédant</h3>
                        <p class="mb-4">
                            Clara et Léo, 28 et 30 ans, ont un projet d'achat de leur première maison.
                        </p>
                    </div>
                </section>

                <section id="module-10" class="bg-white rounded-xl shadow-lg overflow-hidden module-color-9 border-l-8 border-teal-500">
                    <div class="module-header p-6 flex justify-between items-center bg-teal-100/30">
                        <h2 class="text-2xl font-bold flex items-center text-teal-600">
                            <i class="fas fa-book-reader text-teal-600 mr-4"></i> Module 10 : Glossaire & Quizz Général
                        </h2>
                        <i class="fas fa-chevron-down text-teal-600 toggle-icon transition-transform duration-300"></i>
                    </div>
                    <div class="module-content p-6 text-gray-700">
                        <h3 class="text-xl font-semibold mb-4 text-teal-600">Glossaire</h3>
                        <p class="mb-4">
                            Cliquez sur un terme pour voir sa définition.
                        </p>
                        <div class="flex flex-wrap gap-2 mb-4">
                            <button onclick="showDefinition('ITT')" class="bg-gray-200 px-4 py-2 rounded-full text-sm font-semibold hover:bg-gray-300 transition-colors">ITT</button>
                            <button onclick="showDefinition('NPS')" class="bg-gray-200 px-4 py-2 rounded-full text-sm font-semibold hover:bg-gray-300 transition-colors">NPS</button>
                            <button onclick="showDefinition('AIDA')" class="bg-gray-200 px-4 py-2 rounded-full text-sm font-semibold hover:bg-gray-300 transition-colors">AIDA</button>
                            <button onclick="showDefinition('LoiLemoine')" class="bg-gray-200 px-4 py-2 rounded-full text-sm font-semibold hover:bg-gray-300 transition-colors">Loi Lemoine</button>
                            <button onclick="showDefinition('PTIA')" class="bg-gray-200 px-4 py-2 rounded-full text-sm font-semibold hover:bg-gray-300 transition-colors">PTIA</button>
                            <button onclick="showDefinition('AERAS')" class="bg-gray-200 px-4 py-2 rounded-full text-sm font-semibold hover:bg-gray-300 transition-colors">AERAS</button>
                            <button onclick="showDefinition('Délégation')" class="bg-gray-200 px-4 py-2 rounded-full text-sm font-semibold hover:bg-gray-300 transition-colors">Délégation</button>
                        </div>
                        <div id="glossary-definition" class="hidden bg-gray-100 p-4 rounded-lg shadow-inner">
                            <h4 id="glossary-title" class="font-bold text-lg text-teal-600"></h4>
                            <p id="glossary-text"></p>
                        </div>

                        <hr class="my-6 border-gray-300">

                        <h3 class="text-xl font-semibold mb-4 text-teal-600">Quizz Général & Certificat</h3>
                        <p class="mb-4">
                            Testez vos connaissances et obtenez un certificat de réussite. Vous devez obtenir au moins 80% de bonnes réponses pour valider la formation.
                        </p>
                        <div class="quiz space-y-4">
                            <form id="quiz-form">
                                <div class="mb-4">
                                    <p class="font-semibold">1. Quelle garantie couvre la perte totale et irréversible d'autonomie ?</p>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q1a" name="q1" value="PTIA" class="radio-button"><label for="q1a">PTIA</label></div>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q1b" name="q1" value="IPP" class="radio-button"><label for="q1b">IPP</label></div>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q1c" name="q1" value="ITT" class="radio-button"><label for="q1c">ITT</label></div>
                                </div>
                                <div class="mb-4">
                                    <p class="font-semibold">2. Quelle est la première étape de la méthode A.I.D.A. ?</p>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q2a" name="q2" value="Désir" class="radio-button"><label for="q2a">Désir</label></div>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q2b" name="q2" value="Attention" class="radio-button"><label for="q2b">Attention</label></div>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q2c" name="q2" value="Action" class="radio-button"><label for="q2c">Action</label></div>
                                </div>
                                <div class="mb-4">
                                    <p class="font-semibold">3. La garantie perte d'emploi est-elle obligatoire ?</p>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q3a" name="q3" value="Oui" class="radio-button"><label for="q3a">Oui</label></div>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q3b" name="q3" value="Non" class="radio-button"><label for="q3b">Non</label></div>
                                </div>
                                <div class="mb-4">
                                    <p class="font-semibold">4. L'invalidité permanente partielle (IPP) couvre quel taux d'invalidité ?</p>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q4a" name="q4" value="Moins de 33%" class="radio-button"><label for="q4a">Moins de 33%</label></div>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q4b" name="q4" value="Entre 33% et 66%" class="radio-button"><label for="q4b">Entre 33% et 66%</label></div>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q4c" name="q4" value="Plus de 66%" class="radio-button"><label for="q4c">Plus de 66%</label></div>
                                </div>
                                <div class="mb-4">
                                    <p class="font-semibold">5. Qu'est-ce qu'un Net Promoter Score (NPS) ?</p>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q5a" name="q5" value="Un indicateur de vente" class="radio-button"><label for="q5a">Un indicateur de vente</label></div>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q5b" name="q5" value="Un indicateur de fidélité client" class="radio-button"><label for="q5b">Un indicateur de fidélité client</label></div>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q5c" name="q5" value="Un indicateur de communication" class="radio-button"><label for="q5c">Un indicateur de communication</label></div>
                                </div>
                                <div class="mb-4">
                                    <p class="font-semibold">6. La délégation d'assurance permet-elle de changer d'assurance de prêt à tout moment ?</p>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q6a" name="q6" value="Oui, grâce à la loi Lemoine" class="radio-button"><label for="q6a">Oui, grâce à la loi Lemoine</label></div>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q6b" name="q6" value="Non, seulement à la date anniversaire" class="radio-button"><label for="q6b">Non, seulement à la date anniversaire</label></div>
                                </div>
                                <div class="mb-4">
                                    <p class="font-semibold">7. Quel est l'objectif principal de la communication efficace selon le module 7 ?</p>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q7a" name="q7" value="Parler plus vite" class="radio-button"><label for="q7a">Parler plus vite</label></div>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q7b" name="q7" value="Créer une connexion et comprendre les besoins" class="radio-button"><label for="q7b">Créer une connexion et comprendre les besoins</label></div>
                                </div>
                                <div class="mb-4">
                                    <p class="font-semibold">8. Quelle garantie prend en charge les mensualités en cas d'arrêt de travail temporaire ?</p>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q8a" name="q8" value="La PTIA" class="radio-button"><label for="q8a">La PTIA</label></div>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q8b" name="q8" value="L'ITT" class="radio-button"><label for="q8b">L'ITT</label></div>
                                </div>
                                <div class="mb-4">
                                    <p class="font-semibold">9. Quel est l'un des piliers de la négociation d'un prêt selon le module 2 ?</p>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q9a" name="q9" value="Le prix de la maison" class="radio-button"><label for="q9a">Le prix de la maison</label></div>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q9b" name="q9" value="L'assurance emprunteur" class="radio-button"><label for="q9b">L'assurance emprunteur</label></div>
                                </div>
                                <div class="mb-4">
                                    <p class="font-semibold">10. Quel est l'un des avantages de la délégation d'assurance pour le client ?</p>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q10a" name="q10" value="Un prix souvent plus élevé" class="radio-button"><label for="q10a">Un prix souvent plus élevé</label></div>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q10b" name="q10" value="Des économies potentielles" class="radio-button"><label for="q10b">Des économies potentielles</label></div>
                                </div>
                                <div class="mb-4">
                                    <p class="font-semibold">11. Laquelle de ces valeurs n'est pas mentionnée pour le cabinet SADASSUR ?</p>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q11a" name="q11" value="L'innovation" class="radio-button"><label for="q11a">L'innovation</label></div>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q11b" name="q11" value="La transparence" class="radio-button"><label for="q11b">La transparence</label></div>
                                </div>
                                <div class="mb-4">
                                    <p class="font-semibold">12. Quel est l'objet de l'assurance emprunteur ?</p>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q12a" name="q12" value="Garantir le remboursement d'un prêt" class="radio-button"><label for="q12a">Garantir le remboursement d'un prêt</label></div>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q12b" name="q12" value="Couvrir les dégâts des eaux" class="radio-button"><label for="q12b">Couvrir les dégâts des eaux</label></div>
                                </div>
                                <div class="mb-4">
                                    <p class="font-semibold">13. Qu'est-ce que la Loi Lemoine permet ?</p>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q13a" name="q13" value="De résilier son assurance à la date anniversaire" class="radio-button"><label for="q13a">De résilier son assurance à la date anniversaire</label></div>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q13b" name="q13" value="De résilier son assurance à tout moment" class="radio-button"><label for="q13b">De résilier son assurance à tout moment</label></div>
                                </div>
                                <div class="mb-4">
                                    <p class="font-semibold">14. Quel cas pratique aborde le scénario d'un client avec des risques de santé ?</p>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q14a" name="q14" value="Cas Pratique #1" class="radio-button"><label for="q14a">Cas Pratique #1</label></div>
                                    <div class="flex items-center space-x-2"><input type="radio" id="q14b" name="q14" value="Cas Pratique #2" class="radio-button"><label for="q14b">Cas Pratique #2</label></div>
                                </div>
                                
                                <div class="mt-6">
                                    <label for="candidate-name" class="block font-semibold mb-2">Votre nom complet :</label>
                                    <input type="text" id="candidate-name" placeholder="Alaa Rennaoui" class="w-full p-2 rounded-md border border-gray-300">
                                </div>
                            </form>
                            <button id="submit-quiz-btn" onclick="submitQuiz()" class="w-full py-2 px-4 bg-teal-600 text-white rounded-md shadow-md hover:bg-teal-700 transition-colors">Soumettre le Quiz</button>
                            <div id="quiz-result" class="mt-4 text-center text-lg font-semibold"></div>
                            <button id="download-certificate-btn" onclick="generateCertificate()" class="hidden w-full py-2 px-4 bg-teal-600 text-white rounded-md shadow-md hover:bg-teal-700 transition-colors mt-4">
                                <i class="fas fa-download mr-2"></i> Télécharger le Certificat
                            </button>
                            <div class="certificate-container mt-8">
                                <canvas id="certificateCanvas" class="hidden" width="800" height="600"></canvas>
                            </div>
                        </div>
                    </div>
                </section>
            </div>
        </main>
    </div>

    <!-- Pied de page avec des informations de base -->
    <footer class="bg-gray-900 text-white shadow-inner py-4 px-6 md:px-12 mt-auto text-center">
        <h2 class="text-xl md:text-2xl font-bold mb-1">Formation SADASSUR</h2>
        <p class="text-sm">Élaboré par : Alaa Rennaoui</p>
    </footer>

    <script>
        // Objet pour gérer les définitions du glossaire
        const glossary = {
            'ITT': {
                title: 'Incapacité Temporaire Totale de travail',
                definition: 'Garantie qui prend le relais de l’emprunteur pendant une période d’arrêt de travail totale, consécutive à une maladie ou un accident.'
            },
            'NPS': {
                title: 'Net Promoter Score',
                definition: 'Indicateur de mesure de la satisfaction et de la fidélité client. Il est basé sur une simple question : "Sur une échelle de 0 à 10, quelle est la probabilité que vous recommandiez notre entreprise à un ami ou un collègue ?"'
            },
            'Accroche': {
                title: 'Technique d\'Accroche',
                definition: 'Une phrase ou une approche utilisée au début d\'un entretien de vente pour capter l\'attention du prospect et susciter son intérêt pour la conversation.'
            },
            'PTIA': {
                title: 'Perte Totale et Irréversible d\'Autonomie',
                definition: 'Garantie couvrant le remboursement du prêt si l\'emprunteur se trouve dans un état d\'invalidité totale nécessitant l\'assistance d\'une tierce personne.'
            },
            'IPT': {
                title: 'Invalidité Permanente Totale',
                definition: 'Garantie qui s\'active en cas d\'invalidité suite à une maladie ou un accident, avec un taux d\'incapacité supérieur ou égal à 66%.'
            },
            'IPP': {
                title: 'Invalidité Permanente Partielle',
                definition: 'Garantie qui s\'active en cas d\'invalidité suite à une maladie ou un accident, avec un taux d\'incapacité compris entre 33% et 66%.'
            },
            'AIDA': {
                title: 'Méthode A.I.D.A.',
                definition: 'Acronyme de Attention, Intérêt, Désir, Action. C\'est une approche de vente structurée pour guider un prospect vers la décision d\'achat.'
            },
            'LoiLemoine': {
                title: 'Loi Lemoine',
                definition: 'Loi qui permet de résilier à tout moment son contrat d\'assurance emprunteur, sans frais ni pénalités, sous réserve d\'avoir un contrat d\'assurance présentant un niveau de garantie au moins équivalent.'
            },
            'Sinistre': {
                title: 'Sinistre',
                definition: 'Événement garanti par un contrat d\'assurance, comme un décès, un accident ou une maladie, qui donne lieu à une prise en charge par l\'assureur.'
            },
            'TauxAnnuel': {
                title: 'Taux annuel',
                definition: 'Pourcentage appliqué annuellement sur le capital restant dû du prêt pour calculer la prime d\'assurance.'
            },
            'Quotite': {
                title: 'Quotité',
                definition: 'Part de capital assuré par chaque emprunteur dans un prêt à plusieurs. La somme des quotités doit être égale à 100%.'
            },
            'TAEG': {
                title: 'Taux Annuel Effectif Global',
                definition: 'Taux qui inclut tous les coûts d\'un crédit (taux d\'intérêt nominal, frais de dossier, coût de l\'assurance, etc.) pour donner une vision complète du coût total.'
            },
            'AERAS': {
                title: 'Convention AERAS',
                definition: 'S\'Assurer et Emprunter avec un Risque Aggravé de Santé. Convention visant à faciliter l\'accès à l\'assurance de prêt pour les personnes présentant un risque de santé aggravé.'
            },
            'Délégation': {
                title: 'Délégation d\'assurance',
                definition: 'Fait de souscrire son assurance emprunteur auprès d\'un assureur externe à la banque qui octroie le prêt. Cette pratique est légale et permet souvent de réaliser des économies.'
            }
        };

        // Réponses correctes pour le quiz général
        const correctAnswers = {
            'q1': 'PTIA',
            'q2': 'Attention',
            'q3': 'Non',
            'q4': 'Entre 33% et 66%',
            'q5': 'Un indicateur de fidélité client',
            'q6': 'Oui, grâce à la loi Lemoine',
            'q7': 'Créer une connexion et comprendre les besoins',
            'q8': 'L\'ITT',
            'q9': 'L\'assurance emprunteur',
            'q10': 'Des économies potentielles',
            'q11': 'L\'innovation',
            'q12': 'Garantir le remboursement d\'un prêt',
            'q13': 'De résilier son assurance à tout moment',
            'q14': 'Cas Pratique #1'
        };

        // Fonction pour afficher une définition du glossaire
        function showDefinition(termKey) {
            const term = glossary[termKey];
            const definitionContainer = document.getElementById('glossary-definition');
            const titleElement = document.getElementById('glossary-title');
            const textElement = document.getElementById('glossary-text');

            if (term) {
                titleElement.textContent = term.title;
                textElement.textContent = term.definition;
                definitionContainer.classList.remove('hidden');
            }
        }

        // Fonction pour soumettre et noter le quiz général
        function submitQuiz() {
            let score = 0;
            const quizForm = document.getElementById('quiz-form');
            const resultDiv = document.getElementById('quiz-result');
            const downloadBtn = document.getElementById('download-certificate-btn');
            const candidateName = document.getElementById('candidate-name').value;
            const quizQuestions = Object.keys(correctAnswers);
            const totalQuestions = quizQuestions.length;

            if (!candidateName.trim()) {
                resultDiv.innerHTML = '<span class="incorrect-answer-label"><i class="fas fa-exclamation-circle"></i> Veuillez entrer votre nom pour soumettre le quiz.</span>';
                downloadBtn.classList.add('hidden');
                return;
            }

            quizQuestions.forEach(questionName => {
                const selectedAnswer = quizForm.querySelector(`input[name="${questionName}"]:checked`);
                if (selectedAnswer && selectedAnswer.value === correctAnswers[questionName]) {
                    score++;
                }
            });
            
            const percentage = (score / totalQuestions) * 100;

            if (percentage >= 80) {
                resultDiv.innerHTML = `<span class="correct-answer-label"><i class="fas fa-check-circle"></i> Félicitations ! Vous avez réussi le quiz avec un score de ${score}/${totalQuestions} (${percentage.toFixed(0)}%). Vous pouvez maintenant télécharger votre certificat.</span>`;
                downloadBtn.classList.remove('hidden');
            } else {
                resultDiv.innerHTML = `<span class="incorrect-answer-label"><i class="fas fa-times-circle"></i> Malheureusement, vous n'avez pas réussi le quiz. Votre score est de ${score}/${totalQuestions} (${percentage.toFixed(0)}%). Veuillez revoir les modules et réessayer.</span>`;
                downloadBtn.classList.add('hidden');
            }
        }

        // Fonction pour générer le certificat et le télécharger
        function generateCertificate() {
            const canvas = document.getElementById('certificateCanvas');
            const ctx = canvas.getContext('2d');
            const candidateName = document.getElementById('candidate-name').value;

            // Afficher le canvas
            canvas.classList.remove('hidden');

            // Nettoyer le canvas
            ctx.clearRect(0, 0, canvas.width, canvas.height);

            // Créer le fond et les bordures
            ctx.fillStyle = '#fefefe';
            ctx.fillRect(0, 0, canvas.width, canvas.height);
            ctx.strokeStyle = '#0d9488';
            ctx.lineWidth = 10;
            ctx.strokeRect(20, 20, canvas.width - 40, canvas.height - 40);

            // Titre du certificat
            ctx.fillStyle = '#1f2937';
            ctx.font = 'bold 36px Inter, sans-serif';
            ctx.textAlign = 'center';
            ctx.fillText('Certificat de Réussite', canvas.width / 2, 100);

            // Ligne de séparation
            ctx.strokeStyle = '#6b7280';
            ctx.lineWidth = 2;
            ctx.beginPath();
            ctx.moveTo(canvas.width / 2 - 150, 130);
            ctx.lineTo(canvas.width / 2 + 150, 130);
            ctx.stroke();

            // Texte de félicitations
            ctx.font = '24px Inter, sans-serif';
            ctx.fillText('Ce certificat atteste que', canvas.width / 2, 200);

            // Nom du candidat
            ctx.font = 'bold 48px Inter, sans-serif';
            ctx.fillStyle = '#10b981';
            ctx.fillText(candidateName.toUpperCase(), canvas.width / 2, 280);

            // Texte de complétion
            ctx.font = '24px Inter, sans-serif';
            ctx.fillStyle = '#1f2937';
            ctx.fillText('a complété avec succès la formation', canvas.width / 2, 360);
            ctx.font = 'bold 30px Inter, sans-serif';
            ctx.fillText('SADASSUR | Assurance Emprunteur', canvas.width / 2, 400);

            // Date
            const today = new Date();
            const dateString = `Le ${today.getDate()}/${today.getMonth() + 1}/${today.getFullYear()}`;
            ctx.font = '20px Inter, sans-serif';
            ctx.fillText(dateString, canvas.width / 2, 480);

            // Signature
            ctx.font = '20px Inter, sans-serif';
            ctx.fillText('Alaa Rennaoui', canvas.width / 2, 530);
            ctx.fillText('Élaborateur de la formation', canvas.width / 2, 560);

            // Télécharger le certificat
            const image = canvas.toDataURL("image/png").replace("image/png", "image/octet-stream");
            const link = document.createElement('a');
            link.download = `Certificat_SADASSUR_${candidateName.replace(/\s/g, '_')}.png`;
            link.href = image;
            document.body.appendChild(link);
            link.click();
            document.body.removeChild(link);
        }

        // Fonction pour calculer et afficher le graphique des primes
        function calculateAndRenderChart() {
            const initialRate = parseFloat(document.getElementById('initial-rate').value) / 100;
            const sadassurRate = parseFloat(document.getElementById('sadassur-rate').value) / 100;
            const loanAmount = parseFloat(document.getElementById('loan-amount').value);
            const duration = parseInt(document.getElementById('duration').value, 10);
            
            // Calcul simplifié des primes totales
            const initialTotal = loanAmount * initialRate * duration;
            const sadassurTotal = loanAmount * sadassurRate * duration;

            const chartData = {
                labels: ['Prime initiale', 'Prime SADASSUR', 'Économie potentielle'],
                datasets: [{
                    label: 'Montant en euros (€)',
                    data: [initialTotal, sadassurTotal, initialTotal - sadassurTotal],
                    backgroundColor: ['#f59e0b', '#10b981', '#3b82f6'],
                    borderColor: '#fff',
                    borderWidth: 2,
                    borderRadius: 10
                }]
            };

            const chartConfig = {
                type: 'bar',
                data: chartData,
                options: {
                    responsive: true,
                    plugins: {
                        legend: {
                            display: false,
                        },
                        tooltip: {
                            callbacks: {
                                label: function(context) {
                                    let label = context.dataset.label || '';
                                    if (label) {
                                        label += ': ';
                                    }
                                    if (context.parsed.y !== null) {
                                        label += new Intl.NumberFormat('fr-FR', { style: 'currency', currency: 'EUR' }).format(context.parsed.y);
                                    }
                                    return label;
                                }
                            }
                        }
                    },
                    scales: {
                        y: {
                            beginAtZero: true,
                            ticks: {
                                callback: function(value) {
                                    return value.toLocaleString('fr-FR') + ' €';
                                }
                            }
                        }
                    }
                }
            };
            
            // Détruire le graphique existant s'il y en a un pour éviter les superpositions
            if (window.sadassurChartInstance) {
                window.sadassurChartInstance.destroy();
            }

            // Créer le nouveau graphique
            const ctx = document.getElementById('sadassurChart').getContext('2d');
            window.sadassurChartInstance = new Chart(ctx, chartConfig);
        }

        // Événement pour le bouton de calcul du simulateur
        document.getElementById('calculate-btn').addEventListener('click', calculateAndRenderChart);

        // Gestion des modules repliables
        document.querySelectorAll('.module-header').forEach(header => {
            header.addEventListener('click', () => {
                const content = header.nextElementSibling;
                const icon = header.querySelector('.toggle-icon');
                content.classList.toggle('active');
                icon.classList.toggle('rotate-180');
            });
        });

        // Gestion du défilement et de la surbrillance des liens de la table des matières
        document.querySelectorAll('a.toc-link').forEach(link => {
            link.addEventListener('click', (e) => {
                e.preventDefault();
                const targetId = link.getAttribute('href').substring(1);
                const targetSection = document.getElementById(targetId);
                if (targetSection) {
                    targetSection.scrollIntoView({ behavior: 'smooth', block: 'start' });
                }
            });
        });

        // Intersection Observer pour surligner le lien actif
        const sections = document.querySelectorAll('section[id]');
        const options = {
            root: null,
            rootMargin: '-50% 0px -50% 0px', // Le lien s'active au milieu de la fenêtre
            threshold: 0
        };
        const observer = new IntersectionObserver((entries, observer) => {
            entries.forEach(entry => {
                const id = entry.target.getAttribute('id');
                const link = document.querySelector(`a[href="#${id}"]`);
                if (entry.isIntersecting) {
                    document.querySelectorAll('a.toc-link').forEach(l => l.classList.remove('active'));
                    link.classList.add('active');
                }
            });
        }, options);

        sections.forEach(section => {
            observer.observe(section);
        });
    </script>
</body>
</html>
