<script>
  import { onMount } from "svelte";
  import Mail from "@lucide/svelte/icons/mail";
  import ChevronLeft from "@lucide/svelte/icons/chevron-left";
  import ChevronRight from "@lucide/svelte/icons/chevron-right";
  import Play from "@lucide/svelte/icons/play";
  import X from "@lucide/svelte/icons/x";
  import { GithubIcon, LinkedInIcon } from "./icon";
  import profilePhoto from "./assets/pic.jpg";

  const careerStartYear = 2020;
  const yearsOfExperience = new Date().getFullYear() - careerStartYear;

  /** @param {Date} date */
  function formatJakartaTime(date) {
    return new Intl.DateTimeFormat("en-US", {
      timeZone: "Asia/Jakarta",
      hour: "numeric",
      minute: "2-digit",
      hour12: true,
    }).format(date);
  }

  let jakartaTime = formatJakartaTime(new Date());

  onMount(() => {
    const intervalId = window.setInterval(() => {
      jakartaTime = formatJakartaTime(new Date());
    }, 60_000);

    return () => window.clearInterval(intervalId);
  });

  const projects = [
    {
      title: "Psychological Assessment Platform",
      eyebrow: "Assessment & Psychology",
      tone: "clay",
      stories: [
        {
          label: "01 — The beginning",
          title:
            "It started with a simple idea: make psychological testing accessible online.",
          body: "In 2021, I joined the project as a frontend developer, building the platform from the ground up with Vue and Vuetify.",
        },
        {
          label: "02 — Growing fast",
          title: "Then the users came. And kept coming.",
          body: "As adoption grew, the original PHP backend began struggling under the increasing load. The system needed more than just new features. It needed a stronger foundation.",
        },
        {
          label: "03 — Going beyond frontend",
          title: "I started building beyond the interface.",
          body: "I took on the backend as well, helping migrate the core system from PHP to Go with a focus on scalability, reliability, and long-term performance.",
        },
        {
          label: "04 — A stable foundation",
          title: "The result was a system built to handle growth.",
          body: "After the migration, the platform became significantly more stable and capable of supporting a growing number of users without the limitations of the old architecture.",
        },
        {
          label: "05 — More than fixing bugs",
          title:
            "I didn't want it to simply work. I wanted it to keep getting better.",
          body: "Over the years, I continuously introduced improvements based on real-world problems, from handling screen blur and user inactivity to strengthening the overall testing experience.",
        },
        {
          label: "06 — Keeping tests honest",
          title:
            "Then came a bigger challenge: knowing what happens outside the screen.",
          body: "I introduced face recognition and periodic participant snapshots to help proctors monitor test sessions and identify potential irregularities.",
        },
        {
          label: "07 — Human in the loop",
          title: "Automation helps. People still make the final call.",
          body: "The platform doesn't replace proctors. It gives them better visibility, while human supervision remains part of the assessment process.",
        },
        {
          label: "08 — Still evolving",
          title: "The project is still growing, and so am I.",
          body: "New psychological instruments continue to be added, while the platform keeps evolving around the needs of participants, psychologists, administrators, and proctors.",
        },
        {
          label: "09 — What I built",
          title: "From a frontend role to owning the system end-to-end.",
          body: "What began as a frontend project became one of the longest-running systems I've worked on, shaping how I think about scalability, reliability, and building software that lasts.",
        },
      ],
    },
    {
      title: "HIMPSI — Professional Management Platform",
      eyebrow: "People & Professional Services",
      tone: "purple",
      stories: [
        {
          label: "01 — The beginning",
          title:
            "It started as a simple membership system for psychologists across Indonesia.",
          body: "The platform handled membership records, regional transfers, renewals, and other routine administrative needs. Straightforward enough.",
        },
        {
          label: "02 — Things got serious",
          title:
            "Then we built something that directly affected their profession.",
          body: "The platform expanded to handle professional practice permit renewals. Suddenly, a small mistake was no longer just a bug. It could affect someone's ability to practice.",
        },
        {
          label: "03 — Rules keep moving",
          title:
            "The hardest part wasn't the code. It was understanding the rules.",
          body: "Requirements changed frequently, and implementing them meant reading lengthy official decrees and translating regulations into precise system logic.",
        },
        {
          label: "04 — Build it. Then change it.",
          title:
            "Sometimes the rules changed faster than the code could breathe.",
          body: "New requirements had to be understood, implemented, tested, and released quickly. I learned to work comfortably in an environment where yesterday's logic could become today's exception.",
        },
        {
          label: "05 — Real-world impact",
          title: "The feature has been running since 2023.",
          body: "It has since supported the issuance of thousands of professional practice permits, turning what started as a challenging feature into a critical part of the platform.",
        },
        {
          label: "06 — Then came professional exams",
          title:
            "The next challenge was helping students become psychologists.",
          body: "We built a professional examination system that manages the process from university students through their professional qualification.",
        },
        {
          label: "07 — No rulebook stays still",
          title: "This time, the rules weren't always clear.",
          body: "Requirements could change from one day to the next, sometimes without a neat specification to follow. The job was to understand the intent, adapt quickly, and make it work.",
        },
        {
          label: "08 — Beyond development",
          title:
            "I wasn't only writing the code. I was listening to the people using it.",
          body: "For both major features, I also worked directly with users as customer support, turning real problems and feedback into improvements.",
        },
        {
          label: "09 — The outcome",
          title: "Software that became part of a professional journey.",
          body: "The systems are now in maintenance, with thousands of permits issued and hundreds of students completing their professional journey toward becoming psychologists.",
        },
        {
          label: "10 — What it taught me",
          title: "Good software isn't built from requirements alone.",
          body: "Sometimes you have to understand the rules, the people, the pressure, and the consequences behind them. Then turn all of that into something that simply works.",
        },
      ],
    },
    {
      title: "And Much, Much More",
      eyebrow: "A Collection of Challenging Projects",
      tone: "ink",
      stories: [
        {
          label: "Learning should be structured, but never complicated.",
          title: "LMS",
          body: "Built an LMS for Tanoto Foundation, focused on delivering a clear and accessible learning experience.",
        },
        {
          label: "One dashboard, many things happening behind it.",
          title: "CMS",
          body: "Built a CMS to manage advertising content, B2C online test and training registrations, blogs, and more.",
        },
        {
          label: "Turning scattered business operations into one system.",
          title: "CRM",
          body: "Built an internal CRM to manage clients, products, transactions, and the day-to-day operations behind them.",
        },
        {
          label: "A well-defined product with an unforgiving deadline.",
          title: "HRIS",
          body: "The business requirements were clear and carefully structured. The timeline wasn't. We pushed beyond normal hours, stayed committed to the deadline, and delivered what we promised. It was intense, but I'm glad we did it",
        },
      ],
    },
  ];

  /** @type {(typeof projects)[number] | null} */
  let activeProject = null;
  let activeProjectIndex = -1;
  let activeSlide = 0;

  /** @param {(typeof projects)[number]} project */
  function openStory(project) {
    activeProject = project;
    activeProjectIndex = projects.indexOf(project);
    activeSlide = 0;
    document.body.style.overflow = "hidden";
  }

  function closeStory() {
    activeProject = null;
    activeProjectIndex = -1;
    document.body.style.overflow = "";
  }

  function previousStory() {
    if (!activeProject) return;

    if (activeSlide > 0) {
      activeSlide -= 1;
    } else if (activeProjectIndex > 0) {
      activeProjectIndex -= 1;
      activeProject = projects[activeProjectIndex];
      activeSlide = activeProject.stories.length - 1;
    }
  }

  function nextStory() {
    if (!activeProject) return;

    if (activeSlide < activeProject.stories.length - 1) {
      activeSlide += 1;
    } else if (activeProjectIndex < projects.length - 1) {
      activeProjectIndex += 1;
      activeProject = projects[activeProjectIndex];
      activeSlide = 0;
    } else {
      closeStory();
    }
  }

  /** @param {KeyboardEvent} event */
  function handleKeydown(event) {
    if (!activeProject) return;
    if (event.key === "Escape") closeStory();
    if (event.key === "ArrowLeft") previousStory();
    if (event.key === "ArrowRight") nextStory();
  }

  /** @param {MouseEvent} event */
  function handleBackdrop(event) {
    if (event.target === event.currentTarget) closeStory();
  }

  const experiences = [
    {
      period: "2021 — Present",
      role: "Fullstack Developer",
      company: "PT Hara Anargya Indonesia",
      details: [
        "Designed a reusable UI component framework to accelerate development across Vue.js and React.js projects.",
        "Built platforms for membership management, competency testing, and psychological services.",
        "Developed a full-featured HRIS covering employee management, attendance, payroll, and KPI tracking.",
        "Re-engineered an online testing backend from PHP to Go for improved scalability and performance.",
        "Delivered diverse web applications across multiple industries.",
      ],
    },
    {
      period: "2020 — 2021",
      role: "Frontend Developer",
      company: "PT Care Indonesia Solusi",
      details: [
        "Built an online psychometric testing platform with proctoring and real-time messaging using Vue.js and Tailwind CSS.",
        "Developed two LMS applications using Vue.js and Vuetify.",
      ],
    },
  ];
</script>

<svelte:window onkeydown={handleKeydown} />

<svelte:head>
  <title>Akbar Ismail — Fullstack Developer</title>
  <meta
    name="description"
    content="I turn complexity into simple systems that work, matter, and last. Driven by creativity, problem-solving, and resilience."
  />
</svelte:head>

<main>
  <section class="hero section-shell" aria-labelledby="intro-heading">
    <a class="availability" href="mailto:akbarismaiel@gmail.com">
      Available for new opportunities
      <Play size={14} strokeWidth={1.7} aria-hidden="true" />
    </a>

    <div class="intro">
      <h1 id="intro-heading">
        Hi, I'm Akbar Ismail<span aria-hidden="true">,</span>
      </h1>
      <p class="role">Fullstack Developer.</p>
      <p class="summary">
        I turn complexity into simple systems that work, matter, and last.
        Driven by creativity, problem-solving, and resilience.
      </p>
    </div>
  </section>

  <section
    class="section-shell content-section about-section"
    aria-labelledby="about-heading"
  >
    <div class="section-heading">
      <h2 id="about-heading">About</h2>
    </div>

    <div class="about-copy">
      <p>
        I’m a <strong>Full-Stack Developer</strong> with
        <strong>{yearsOfExperience}+ years of experience</strong> turning complex
        ideas into reliable, scalable digital products. I’ve built systems across
        education, HR, psychology, and business operations.
      </p>

      <p>
        My work focuses on <strong>thoughtful architecture</strong>,
        maintainable code, and practical solutions. Creative, solution-oriented,
        and resilient, I enjoy solving difficult problems and continuously
        finding better ways to build.
      </p>
    </div>
  </section>

  <section
    class="section-shell content-section"
    aria-labelledby="projects-heading"
  >
    <div class="section-heading">
      <h2 id="projects-heading">Projects</h2>
      <span>Tap a project to read</span>
    </div>

    <div class="project-grid" id="all-projects">
      {#each projects as project}
        <button
          class={`story-cover ${project.tone}`}
          type="button"
          onclick={() => openStory(project)}
          aria-label={`Open ${project.title} story`}
        >
          <span class="story-count">{project.stories.length} chapters</span>
          <div>
            <span class="story-eyebrow">{project.eyebrow}</span>
            <h3>{project.title}</h3>
          </div>
          <span class="story-cta">
            <span class="story-play" aria-hidden="true">
              <Play size={14} fill="currentColor" />
            </span>
            View story
          </span>
        </button>
      {/each}
    </div>
  </section>

  {#if activeProject}
    <div class="story-overlay" role="presentation" onclick={handleBackdrop}>
      <section
        class={`story-viewer ${activeProject.tone}`}
        role="dialog"
        aria-modal="true"
        aria-label={`${activeProject.title} project story`}
      >
        <div
          class="story-progress"
          style={`grid-template-columns: repeat(${activeProject.stories.length}, minmax(0, 1fr))`}
          aria-label={`Chapter ${activeSlide + 1} of ${activeProject.stories.length}`}
        >
          {#each activeProject.stories as _, index}
            <span class:complete={index <= activeSlide}></span>
          {/each}
        </div>

        <div class="story-viewer-head">
          <div>
            <span>{activeProject.eyebrow}</span>
            <strong>{activeProject.title}</strong>
          </div>
          <button type="button" onclick={closeStory} aria-label="Close story">
            <X size={19} />
          </button>
        </div>

        <div class="story-content">
          <p class="story-label">{activeProject.stories[activeSlide].label}</p>
          <h3>{activeProject.stories[activeSlide].title}</h3>
          <p class="story-body">{activeProject.stories[activeSlide].body}</p>
        </div>

        <button
          class="story-tap-zone story-tap-prev"
          type="button"
          onclick={previousStory}
          disabled={activeProjectIndex === 0 && activeSlide === 0}
          aria-label="Previous chapter"
        >
          <ChevronLeft size={22} />
        </button>
        <button
          class="story-tap-zone story-tap-next"
          type="button"
          onclick={nextStory}
          aria-label="Next chapter"
        >
          <ChevronRight size={22} />
        </button>

        <div class="story-controls">
          <button
            type="button"
            onclick={previousStory}
            disabled={activeProjectIndex === 0 && activeSlide === 0}
            aria-label="Previous chapter"
          >
            <ChevronLeft size={19} />
          </button>
          <span>
            Project {activeProjectIndex + 1}/{projects.length} · {activeSlide +
              1}/{activeProject.stories.length}
          </span>
          <button type="button" onclick={nextStory} aria-label="Next chapter">
            <ChevronRight size={19} />
          </button>
        </div>
      </section>
    </div>
  {/if}

  <section
    class="section-shell content-section experience-section"
    aria-labelledby="experience-heading"
  >
    <div class="section-heading">
      <h2 id="experience-heading">Experience</h2>
    </div>

    <div class="experience-list">
      {#each experiences as experience}
        <article class="experience-item">
          <p class="period">{experience.period}</p>
          <div>
            <h3>{experience.role}</h3>
            <p class="company">{experience.company}</p>
            <ul class="experience-details">
              {#each experience.details as detail}
                <li>{detail}</li>
              {/each}
            </ul>
          </div>
        </article>
      {/each}
    </div>
  </section>

  <section
    class="section-shell content-section personal-section"
    aria-labelledby="personal-heading"
  >
    <div class="personal-layout">
      <div
        class="personal-photo w-[200px] h-[200px] flex items-center justify-center -rotate-6"
      >
        <div class="bg-white p-1 rounded-lg w-fit h-fit rotate-7">
          <img
            src={profilePhoto}
            class="w-[200px] h-[200px] object-cover rounded"
            alt="Akbar Ismail"
          />
        </div>
      </div>

      <div class="personal-copy">
        <p>
          Like you’ve seen above, my name is <strong>Akbar Ismail</strong>. You
          can call me <strong>Ma’il</strong> (pronounced “ma-eel”), not “mail.” But
          don’t overthink it, though.
        </p>

        <p>
          I’m based in <strong>Bandung, Indonesia</strong>, on GMT+7. It’s
          <strong class="current-time">{jakartaTime}</strong> here right now. If you’re somewhere in
          a very different timezone, don’t worry, I’ll still be around. Or even
          better, I’ll be working while you sleep, so you can wake up to the
          task already done. <span aria-label="playful expression">:p</span>
        </p>
      </div>
    </div>
  </section>

  <footer class="section-shell footer">
    <p>Have a project or role in mind?</p>
    <div class="footer-links">
      <a class="footer-email" href="mailto:akbarismaiel@gmail.com">
        <Mail size={16} strokeWidth={1.7} aria-hidden="true" />
        akbarismaiel@gmail.com
      </a>
      <a
        class="social-link"
        href="https://github.com/akbarism"
        target="_blank"
        rel="noreferrer"
        aria-label="Akbar Ismail on GitHub"
      >
        <GithubIcon size={17} />
      </a>
      <a
        class="social-link"
        href="https://www.linkedin.com/in/akbarism/"
        target="_blank"
        rel="noreferrer"
        aria-label="Akbar Ismail on LinkedIn"
      >
        <LinkedInIcon size={17} />
      </a>
    </div>
  </footer>
</main>
