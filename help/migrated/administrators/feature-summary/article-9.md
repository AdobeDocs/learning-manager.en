# Adobe Learning Manager Virtual Coach FAQ

Get answers to frequently asked questions about using Virtual Coach in Adobe Learning Manager.

**What is Virtual Coach?**
Virtual Coach is an AI-powered role-play and coaching feature built into Adobe Learning Manager. It lets learners practice real-world conversations with an AI persona that responds intelligently in real time, then receive an instant performance report covering what they said and how they said it. For a full explanation, see [what virtual coach is](#).

**Who uses Virtual Coach?**
Organizations use Virtual Coach to train sales representatives, customer service teams, call center agents, managers and leaders, new hires, partners, and employees learning new products or processes. Virtual Coach is available to all learners, authors, and administrators in an Adobe Learning Manager account where it's been activated. Learners access and complete role-play sessions, authors create and publish role-play scenarios, and administrators manage credits and view reports.

**Does Virtual Coach automatically use my existing Adobe Learning Manager content?**
No. Authors must provide reference materials, such as playbooks, sales decks, transcripts, and scoring rubrics, or a written prompt, for each role play they create. Virtual Coach uses those uploaded materials and persona definitions to drive the conversation; it doesn't automatically draw on content already in your Content Library or courses. See [gather materials for a virtual coach role play](#) for what to prepare.

**What types of role plays are available?**
Virtual Coach supports three domains: Sales Enablement, Leadership Development, and Skills Assessment. Authors choose from pre-built templates covering scenarios such as B2B discovery calls, cold calls, handling objections, giving difficult feedback, and de-escalating customer complaints. Authors can also create custom scenarios from scratch using the AI assistant. See [create and publish a virtual coach role play](#).

**What languages does Virtual Coach support?**
Virtual Coach is available in nine languages for both the interface and simulation content: German (Germany), Spanish (LATAM), Spanish (Spain), French (France), Italian (Italy), Portuguese (Portugal), Portuguese (Brazil), Dutch (Netherlands), and English.

**How is Virtual Coach licensed and billed?**
Virtual Coach is available as an add-on subscription to Adobe Learning Manager. Usage is measured in Monthly Active Users (MAUs). An MAU credit is consumed when a learner completes a session in a calendar month; additional sessions by the same learner that month don't consume additional credits. Unused credits at the end of the annual contract lapse. See [manage virtual coach usage and billing](#).

**How is a learner's score calculated?**
Each session produces a Knowledge score and a Style score. The Knowledge score reflects whether the learner addressed the required topics and provided accurate information. The Style score reflects how the learner communicated, including pace, clarity, filler words, sentence strength, and vocal energy. Authors set the weight of each component when configuring the scenario; a common configuration is 70% Knowledge and 30% Style. See [understand your virtual coach performance report](#).

**Can learners download their performance report?**
Yes. In addition to viewing the report on screen, learners can download it as a PDF to keep for their own records or share with a manager.

**Can a learner retry a role play?**
Yes. Learners can attempt a role play as many times as they want. Each attempt is a new, independent session and generates a new performance report. Only the first session in a calendar month consumes an MAU credit.

**Can learners submit their sessions for human review?**
No.

**Is Virtual Coach available on mobile?**
Virtual Coach is supported on the Adobe Learning Manager desktop and mobile web, and by APIs. It's not available in the Adobe Learning Manager mobile app (iOS/Android) in the current release.

**Is learner data used to train the AI?**
No. Virtual Coach is hosted on GDPR-compliant infrastructure, and no personal learner data is used to train AI models.

**What's the difference between a job aid and a course module for Virtual Coach?**
A job aid is a standalone, on-demand resource that learners can access directly from the Catalog at any time without being enrolled in a course. A course module is accessed as part of a structured course sequence with enrollment, completion tracking, and formal assessment. The same role play can be published as a job aid and added to multiple courses simultaneously. See [add a virtual coach role play to a course](#).

**How should we package Virtual Coach when rolling out a new process or product?**
Package the role play inside a course or learning journey alongside the related training content, and distribute the course link through email or other change-management communications. Virtual Coach works best positioned as the last mile of training — the checkpoint right after learners complete related content, where they demonstrate they can apply it, rather than as a standalone activity.

**Is Virtual Coach supported on headless or API implementations?**
Public APIs for fetching courses and job aids also fetch Virtual Coach courses and job aids. The `jobAidType` filter is available for fetching Virtual Coach job aids specifically. Virtual Coach content is supported in the headless player, and courses and job aids containing Virtual Coach work in the fluidic player.

For questions about building and configuring a role play, see the [Virtual Coach authoring FAQ](#).
