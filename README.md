<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>wakeem.dev — Portfolio</title>

<style>
/* ===========================
   GLOBAL RESET + BODY
   =========================== */

body {
    margin: 0;
    background: #05060b;
    color: #e5f4ff;
    font-family: Consolas, "Fira Code", monospace;
}

.glow {
    text-shadow: 0 0 12px rgba(0,255,200,0.6);
}







/* ===========================
   HEADER + NAVIGATION
   =========================== */

header {
    padding: 40px;
    border-bottom: 1px solid #1b2338;
    background: radial-gradient(circle at top left, #10182a 0, #05060b 60%, #020308 100%);
    box-shadow: 0 0 25px rgba(0,255,200,0.18);
}

nav a {
    color: #e5f4ff;
    text-decoration: none;
    padding: 6px 12px;
    border: 1px solid #28345a;
    border-radius: 999px;
    margin-right: 8px;
    background: linear-gradient(135deg, rgba(0,255,200,0.08), rgba(0,140,255,0.08));
    font-size: 13px;
    transition: 0.2s;
}

nav a:hover {
    background: rgba(0,255,200,0.18);
    border-color: #6af7d4;
}







/* ===========================
   PANELS + TERMINAL
   =========================== */

.container {
    max-width: 1100px;
    margin: 30px auto;
    padding: 20px;
}

.panel {
    background: linear-gradient(145deg, #050814, #05060b);
    border: 1px solid #1b2338;
    border-radius: 14px;
    padding: 20px;
    margin-bottom: 25px;
    box-shadow: 0 0 18px rgba(0,0,0,0.7);
}

.panel h2 {
    margin-top: 0;
    color: #ffffff;
}

.tag {
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.18em;
    color: #7a8cff;
    margin-bottom: 8px;
}

.terminal {
    background: rgba(2,10,25,0.9);
    border: 1px solid #18233c;
    padding: 14px;
    border-radius: 10px;
    font-size: 14px;
    margin-top: 20px;
}

.terminal span {
    color: #6af7d4;
}

footer {
    text-align: center;
    padding: 20px;
    font-size: 12px;
    color: #5f6c9b;
    border-top: 1px solid #141a2b;
    margin-top: 40px;
}







/* ===========================
   COLLAPSIBLE SECTIONS (BIG)
   =========================== */

.section-details {
    border-radius: 14px;
    border: 1px solid #1b2338;
    background: linear-gradient(145deg, #050814, #05060b);
    padding: 14px 16px 16px;
    margin-bottom: 25px;
    box-shadow: 0 0 18px rgba(0,0,0,0.7);
}

.section-details[open] {
    border-color: #6af7d4;
    box-shadow: 0 0 22px rgba(0,255,200,0.35);
}

.section-details summary {
    list-style: none;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.summary-left {
    display: flex;
    flex-direction: column;
}

.summary-title {
    font-size: 22px;
    color: #ffffff;
}

.summary-tag {
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.18em;
    color: #7a8cff;
}

.summary-icon {
    font-size: 18px;
    color: #6af7d4;
    transition: transform 0.2s;
}

.section-details[open] .summary-icon {
    transform: rotate(90deg);
}

.collapsible-body {
    opacity: 0;
    margin-top: 14px;
}







/* ===========================
   COLLAPSIBLE LOGS (SMALL)
   =========================== */

.achievement details {
    border-radius: 10px;
    border: 1px solid #28345a;
    background: rgba(3,10,25,0.9);
    padding: 10px 12px;
    margin-bottom: 10px;
    transition: 0.2s;
}

.achievement details[open] {
    border-color: #6af7d4;
    box-shadow: 0 0 14px rgba(0,255,200,0.25);
}

.achievement summary {
    list-style: none;
    cursor: pointer;
    display: flex;
    justify-content: space-between;
    align-items: center;
    color: #e5f4ff;
    font-size: 16px;
}

.achievement summary::-webkit-details-marker {
    display: none;
}

.ach-icon {
    font-size: 16px;
    color: #6af7d4;
    transition: transform 0.2s;
}
 

.about-body {
    margin-top: 8px;
    font-size: 15px;
    color: #9fb3ff;
    line-height: 1.5;
}

.achievement-body {
    opacity: 0;
    margin-top: 8px;
    font-size: 15px;
    color: #9fb3ff;
    line-height: 1.5;
}







/* ===========================
   ANIMATIONS + EFFECTS
   =========================== */

/* Typing effect */
.typing {
    width: 0;
    overflow: hidden;
    white-space: nowrap;
    border-right: 2px solid #6af7d4;
    animation: typing 1.5s steps(12) forwards, blink 0.7s infinite;
}

@keyframes typing {
    from { width: 0; }
    to { width: 210px; }
}

@keyframes blink {
    50% { border-color: transparent; }
}

/* Replayable collapsible animation */
.animate-open {
    animation: slideDown 0.75s ease-in-out;
    opacity: 1;
}

@keyframes slideDown {
    from {
        opacity: 0;
        transform: translateY(-6px);
    }
    to {
        opacity: 1 !important;
        transform: translateY(0);
    }
}

/* Neon pulse */
.section-details[open],
.achievement details[open] {
    animation: neonPulse 0.6s ease-out;
}

@keyframes neonPulse {
    0% { box-shadow: 0 0 0px rgba(0,255,200,0.0); }
    50% { box-shadow: 0 0 22px rgba(0,255,200,0.35); }
    100% { box-shadow: 0 0 14px rgba(0,255,200,0.25); }
}

/* Glitch hover */
.summary-title:hover {
    animation: glitch 0.4s steps(2, end);
}

@keyframes glitch {
    0% { text-shadow: 2px 0 #6af7d4, -2px 0 #ffdd7a; }
    20% { text-shadow: -2px 0 #6af7d4, 2px 0 #ffdd7a; }
    40% { text-shadow: 2px 0 #ffdd7a, -2px 0 #6af7d4; }
    60% { text-shadow: -2px 0 #ffdd7a, 2px 0 #6af7d4; }
    100% { text-shadow: none; }
}

</style>
</head>

<body>

<header>
    <h1 class="glow typing">&gt; wakeem<span style="color:#6af7d4;">.dev</span></h1>

    <!--  SEARCH BAR IN HEADER  -->
    <div style="margin-top:20px;">
        <input id="searchBox" 
               type="text" 
               placeholder="Search..." 
               style="width: 260px; padding: 8px 12px; border-radius: 8px; border: 1px solid #28345a; background:#0b0f1c; color:#e5f4ff; font-family:inherit;">
    </div>



    <div style="color:#9fb3ff; font-size:13px;">
        status: <span style="color:#6af7d4;">online</span> • mode: <span style="color:#ffdd7a;">learning & building</span>
    </div>

    <nav style="margin-top:20px;">
        <a href="https://youtu.be/3aTjHUgu4ZA">about</a>
        <a href="#achievements">achievements</a>
        <a href="#projects">projects</a>
        <a href="#contact">contact</a>
    </nav>

    <div class="terminal">
        <div class="tag">terminal</div>
        <span>$</span> whoami<br>
        → aspiring developer | curious mind | always debugging and improving.<br><br>
        <span>$</span> mission<br>
        → I want to understand how things work, build cool stuff, and share what I learn along the way.<br><br>
    </div>
</header>

<div class="container">







<!-- ABOUT -->
<section id="about" class="panel">
    <div class="tag">about_me.json</div>
    <h2>About Me</h2>

    <p>I’m <span style="color:#6af7d4;">wakeem</span>, someone who enjoys solving problems efficiently, experimenting, learning, and figuring out the operating principles of new technology.</p>

    <p><span style="color:#ffdd7a;">Current focus:</span> improving my coding skills, learning new skills - like drawing and graphics design, and creating new projects that challenge me.</p>
    
    <div class="collapsible-about-body achievement">

        <details data-keywords="about me, about">
            <summary>
                Read more about me.
                <span class="ach-icon">&gt;</span>
            </summary>

            <div class="about-body" >
                Ever since I was young, I was always a curious child and loved experimenting with new things. I took apart things to see how they worked. I fixed things. I played with things I probably shouldn't have. <br><br>

                My fascination with technology stemmed from this curiosity. I used to always find stuff to take apart and play with. The first thing I remember being able to understand and put back together was this RC car. It was ~$10 and was around the size of a Hot Wheels car. I was bored and decided to take it apart. After doing so, was somehow able to understand what goes where and how it works. Though, I obviously only knew to an extent what the parts were. I was going based off of theories and not research.<br><br>

                I put it back together and it fully worked, to my surprise. After that, I took apart many things just to put them back together. I even started fixing broken things around the house. And even taking garbage and fixing it or scrapping it for parts. The main thing I used to fix was my Nintendo Switch.<br><br>

                For years it would get broken. Whether it was due to age, or from my brother breaking it, it would get damaged a lot. After years of fixing it, I know it by heart. Another example would be my current laptop. I don’t even have the screws in the laptop case since I tinker with it so much. Mainly because of the fan since it’s defective so I have to tinker it every now and then. <br><br>

                More recently, I have been getting into coding a lot. I got good at it almost immediately and went on to achieve a lot within a short time. My first achievement was getting my Pitt project for CHS programming into one line using list comprehension. This is an intermediate level technique often taught in college, and I did it without any source material. I figured it out just by experimenting. Then, I managed to basically master it. Lastly, I implemented it into my code. And all in less than half an hour.<br><br>

                A more recent achievement of mine would be the making of a Jarvis-like utility based AI. Though not complete, it still has some useful functionality. Like being able to turn off and on my lights and setting reminders. Along with this, I also have been working on a conversation AI, named Sage, that I hope to make more advance and implement more utility into in the near future.<br><br>
            </div>
        </details>

    </div>
</section>






<!-- -----------------------------------------------------------------------      FOR REFERENCE     ----------------------------------------------------------------------------- -->


<!--

THIS IS TO MAKE THE WHOLE OUTER SECTIONS (LIKE THE PROJECTS OR ACHIEVEMENTS) OTHER COLLAPSIBLES GO UNDER THE SUMMARY 

<details class="section-details" id="achievements">       
    <summary>
        <div class="summary-left">
            <div class="summary-tag">academic_achievements.log</div>
            <div class="summary-title">Academic Achievements</div>
        </div>
        <div class="summary-icon">&gt;</div>
    </summary>



</details>

-->

<!---------------------------------------------------------------------->

<!--
    THIS IS TO MAKE ONE INNER COLLAPSIBLE FOR A SUBJECT LIKE CHS PROGRAMMING        STUFF GOES UNDER THE SUMMARY

    <div class="collapsible-body achievement"> 
        <details>
            <summary>
                NAME 
                <span class="ach-icon">&gt;</span>
            </summary>


        </details>
    </div>

-->


<!---------------------------------------------------------------------->

<!--
THIS IS TO MAKE THE COLLAPSIBLE FOR THE SUBJECT   INFORMATION GOES IN THE achievement-body DIV

            <div class="achievement-body">

                <details>
                    <summary>
                        NAME
                        <span class="ach-icon">&gt;</span>
                    </summary>

                    <div class="achievement-body">
                        BODY OR WHATEVER    
                    </div>

                </details>
            </div>

-->

<!---------------------------------------------------------------------->

<!--  This is what it would look like all together  ADD ARROWS BACK TO COMMENTS TO MAKE THEM COMMENTS AGAIN

<!-- OUTER PART TO MAKE THE WHOLE SECTION COLLAPSIBLE --

<details class="section-details" id="achievements">       
    <summary>
        <div class="summary-left">
            <div class="summary-tag">academic_achievements.log</div>
            <div class="summary-title">Academic Achievements</div>
        </div>
        <div class="summary-icon">&gt;</div>
    </summary>


    <!-- INNER PART FOR SUBJECT --

    <div class="collapsible-body achievement"> 
        <details>
            <summary>
                NAME 
                <span class="ach-icon">&gt;</span>
            </summary>


            <!--INNER PART FOR INFORMATION BODY COLLAPSIBLE--

            <div class="achievement-body">

                <details>
                    <summary>
                        NAME
                        <span class="ach-icon">&gt;</span>
                    </summary>

                    <div class="achievement-body">
                        BODY OR WHATEVER    
                    </div>

                </details>
            </div>

        </details>
    </div>



</details>

-->





<!-- ACADEMIC ACHIEVEMENTS -->
<details class="section-details" id="achievements" data-keywords="academic achievements, academic">
    <summary>
        <div class="summary-left">
            <div class="summary-tag">academic_achievements.log</div>
            <div class="summary-title">Academic Achievements</div>
        </div>
        <div class="summary-icon">&gt;</div>
    </summary>

    

    <div class="collapsible-body achievement">

        <details data-keywords="technology achievements, technology related achievements, programming achievements, coding achievements, technology">
            <summary>
                Technology related achievements
                <span class="ach-icon">&gt;</span>
            </summary>





            <div class="achievement-body">
                <details data-keywords="chs programming, chs, programming">
                    <summary>
                        CHS Programming
                        <span class="ach-icon">&gt;</span>
                    </summary>

                    <div class="achievement-body">


                        <!-- INNER COLLAPSIBLE FOR CHS PROGRAMMING-->



                            <!-- PITTS PROJECTS -->

                            <details data-keywords="pitt project 1, pitt project one, pitt one, monty hall, monty hall problem, monty">
                                <summary>
                                    Monty Hall Simulation (Pitt Project 1)
                                    <span class="ach-icon">&gt;</span>
                                </summary>

                                <div class="achievement-body">
                                    For this project, we had to make a program that would simulate the Monty Hall problem (see below for description). It would start with asking how many rounds the user wanted to simulate—between 10 and 10000. Then, it would ask the user if they wanted to switch or stay. Lastly, it would run the simulation and print out how many rounds the player won.
                                    <br>
                                    The Monty Hall problem is a probability puzzle based on a game show scenario. You are presented with three doors: behind one door is a car (the prize you want), and behind the other two doors are goats. You choose one door, but before it’s opened, the host (who knows what’s behind each door) opens another door, revealing a goat. You are then given the option to stick with your original choice or switch to the remaining unopened door. The counterintuitive solution is that switching doors actually gives you a 2/3 chance of winning the car, while sticking with your original choice only gives you a 1/3 chance.
                                    <br>
                                    <iframe width="560" height="315" src="https://www.youtube.com/embed/3aTjHUgu4ZA?si=RYu47L5D-qTSv8OL&amp;start=1" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
                                    <br>
                                    <a href="https://youtu.be/3aTjHUgu4ZA" target="_blank">(Video Link)</a>

                                </div>
                            </details>


                            <details data-keywords="pitt project 2, pitt project two, pitt two, word frequency analysis, word frequency, word analysis, sherlock holmes books">
                                <summary>
                                    Word Frequency Analysis (Pitt Project 2)
                                    <span class="ach-icon">&gt;</span>
                                </summary>

                                <div class="achievement-body">
                                    Analyzed word frequencies in three Sherlock Holmes books, removing common words to reveal unique patterns and insights.
                                </div>
                            </details>

                            <details   data-keywords="pitt project 3, pitt three, pitt project three, flashcard quiz, flashcard">
                                <summary>
                                    Flashcard Quiz Interface (Pitt Project 3)
                                    <span class="ach-icon">&gt;</span>
                                </summary>

                                <div class="achievement-body">
                                    Developed a flashcard quiz application using Object-Oriented Programming, featuring multiple choice, true/false, and short answer questions.
                                </div>
                            </details>





                    </div>
                </details>


            </div>
        </details>



        <details>
            <summary>
                [Course Name] — [Project / Grade]
                <span class="ach-icon">&gt;</span>
            </summary>

            <div class="achievement-body">
                Describe a project, presentation, or assignment you’re proud of.
            </div>
        </details>

        <details>
            <summary>
                [Club / Activity] — [Role or Recognition]
                <span class="ach-icon">&gt;</span>
            </summary>

            <div class="achievement-body">
                Mention leadership, teamwork, or any recognition you received.
            </div>
        </details>

    </div>
</details>









<!-- PERSONAL ACHIEVEMENTS -->
<details class="section-details">
    <summary>
        <div class="summary-left">
            <div class="summary-tag">personal_achievements.log</div>
            <div class="summary-title">Personal Achievements</div>
        </div>
        <div class="summary-icon">&gt;</div>
    </summary>

    <div class="collapsible-body achievement">

        <details>
            <summary>
                hi
                <span class="ach-icon">&gt;</span>
            </summary>

            <div class="achievement-body">
                hi
            </div>
        </details>

        <details>
            <summary>
                Improved problem‑solving skills
                <span class="ach-icon">&gt;</span>
            </summary>

            <div class="achievement-body">
                Treating challenges like debugging sessions: observe, test, iterate, learn.
            </div>
        </details>

        <details>
            <summary>
                hi
                <span class="ach-icon">&gt;</span>
            </summary>

            <div class="achievement-body">
                hhhhhhhi
            </div>
        </details>

    </div>
</details>









<!-- PROJECTS -->
<details class="section-details" id="projects">
    <summary>
        <div class="summary-left">
            <div class="summary-tag">projects.list</div>
            <div class="summary-title">Projects</div>
        </div>
        <div class="summary-icon">&gt;</div>
    </summary>

    <div class="collapsible-body achievement">

        <details>
            <summary>
                Custom HTML/CSS Elements
                <span class="ach-icon">&gt;</span>
            </summary>

            <div class="achievement-body">
                Created 3D headers, decorative dividers, and unique layouts using pure CSS.
            </div>
        </details>

        <details>
            <summary>
                [Project Name]
                <span class="ach-icon">&gt;</span>
            </summary>

            <div class="achievement-body">
                Describe what the project does, what you learned, and what makes it interesting.
            </div>
        </details>

        <details>
            <summary>
                [Experiment / Prototype]
                <span class="ach-icon">&gt;</span>
            </summary>

            <div class="achievement-body">
                Add any small experiments, tests, or creative builds you want to showcase.
            </div>
        </details>

    </div>
</details>









<!-- CONTACT -->
<section id="contact" class="panel">
    <div class="tag">contact.cfg</div>
    <h2>Contact</h2>

    <p>If you’d like to connect or collaborate, you can reach me here:</p>
    <p>Email: <span style="color:#6af7d4;">wakeemlwin09@gmail.com</span></p>
</section>

</div>

<footer>
    © 2026 wakeem • system status: <span style="color:#6af7d4;">running</span>
</footer>





<!--  JS FOR ANIMATION  -->
<script>
document.querySelectorAll("details").forEach(d => {
    d.addEventListener("toggle", () => {
        const body = d.querySelector(".achievement-body, .collapsible-body, .about-body");
        if (!body) return;
        
        // Reset animation
        body.classList.remove("animate-open");
        void body.offsetWidth;

        // Animate when opening
        if (d.open) {
            body.classList.add("animate-open");
        }
    });
});
</script>


<!--  KEYWORD SEARCH SYSTEM  -->
<script>
const searchBox = document.getElementById("searchBox");

searchBox.addEventListener("keydown", function(e) {
    if (e.key !== "Enter") return;

    const query = searchBox.value.trim().toLowerCase();
    if (!query) return;

    const allDetails = document.querySelectorAll("details");
    let found = false;

    allDetails.forEach(d => {
        const keywords = d.dataset.keywords;
        if (!keywords) return;

        const list = keywords.toLowerCase().split(",").map(k => k.trim());

        if (list.includes(query)) {
            found = true;

            // Open this details
            d.open = true;

            // Open all parent <details> (like Academic/Projects sections)
            let parent = d.parentElement;
            while (parent) {
                if (parent.tagName && parent.tagName.toLowerCase() === "details") {
                    parent.open = true;
                }
                parent = parent.parentElement;
            }

            // Scroll to the matched collapsible
            d.scrollIntoView({ behavior: "smooth", block: "center" });

            // Trigger animation replay on its body
            const body = d.querySelector(".achievement-body, .collapsible-body");
            if (body) {
                body.classList.remove("animate-open");
                void body.offsetWidth;
                body.classList.add("animate-open");
            }
        }
    });

    if (!found) {
        alert("No matching section found.");
    }
});
</script>




</body>
</html>
