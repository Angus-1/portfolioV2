<script lang="ts">
  import Card from "$lib/components/Card.svelte";
  import Page from "$lib/components/Page.svelte";
  import { neutralBackground } from "$lib/utils/constants";

  type Job = {
    employer: string;
    title: string;
    startDate: Date;
    endDate: Date;
    description?: string;
    tasks: string[];
    tags?: string[];
  };
  const months = [
    "January",
    "February",
    "March",
    "April",
    "May",
    "June",
    "July",
    "August",
    "September",
    "October",
    "November",
    "December",
  ];
  const currentDate = new Date();
  function dateToString(date: Date) {
    return `${months[date.getMonth()]} ${date.getFullYear()}`;
  }
  function formatDateString(start: Date, end: Date) {
    return `${dateToString(start)} - ${dateToString(end) ?? "Present"}`;
  }
  const jobs: Array<Job> = [
    {
      employer: "Ingram Micro",
      title: "Oracle Database Intern",
      startDate: new Date(2022, 5),
      endDate: new Date(2022, 8),
      
      tasks: [
        "Used ssh to connect to Linux servers and manually create/script oracle 19c prototype database applications",
        "Configured databases for backup and recovery using oracle's built in proprietary RMAN(recovery manager) to protect against data loss",
        "Researched oracle database architecture, as well as the many occuring processes inside a server instance",        
      ],
      tags: [
        "Oracle",
        "Databases",
        "Backup and recovery",
        "Configuration",
        "Linux"
      ],
    },
    {
      employer: "ACM Fullerton",
      title: "Development Officer",
      startDate: new Date(2022, 3),
      endDate: new Date(2020, 7),
      tasks: [
        "Made contributions towards Cal-State-Fullerton's Chapter of Association  for Computing Machinery website's issues",
        "Hosted workshops and crash courses for students to learn development skills, concepts, and tools",
        "Attended weekly meeings to discuss current github issues that need resolving",
      ],
      tags: ["Github", "Web Development",],
    },
    {
      employer: "Db&M Media",
      title: "Data entry and web research specialist",
      startDate: new Date(2021, 8),
      endDate: new Date(2022, 3),
      tasks: [
        "Responsible for creating and maintaining potential client database of over 2000 potential clients",
        "Incorporated a digital filing system that improved clientele follow-up rates",
        "Researched and compiled data on potential high value buyers for company services",
        "Automated process of data entry to be more efficient",
      ],
      tags: ["Python", "Excel","Data Entry"],
    },
    {
      employer: "Santa Ana College Computing Center ",
      title: "Student Tutor",
      startDate: new Date(2019, 1),
      endDate: new Date(2020, 1),
      tasks: [
        "Explained different tiers of C++,such as intro to programming, Programming Concepts and Data Structures to other students",
        "Assisted students with the Java Programming language and its features",
        "Facilitated other students programming projects to confirm they were on course",
      ],
      tags: ["C++", "Java", "Tutor",],
    },
  ];

  export let backgroundClass = neutralBackground;
</script>

<Page id="work" title="Work Experience" {backgroundClass}>
  <div
    class="container mx-auto grid max-w-screen-xl gap-4 md:grid-cols-1 xl:grid-cols-2 3xl:grid-cols-4"
  >
    {#each jobs as job}
      <Card
        title={job.employer}
        subtitle={`${job.title}, ${formatDateString(
          job.startDate,
          job.endDate
        )}`}
        tags={job.tags}
      >
        {#if job.description}
          <div class="mb-1">
            {job.description ?? ""}
          </div>
        {/if}
        <ul class="list-disc list-inside">
          {#each job.tasks as task}
            <li>{task}</li>
          {/each}
        </ul>
      </Card>
    {/each}
  </div>
</Page>


