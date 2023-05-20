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
      employer: "Niagara Bottling",
      title: "Information Technology Intern",
      startDate: new Date(2023, 4),
      endDate: new Date(2023, 8),
      
      tasks: [
        ":D",       
      ],
      tags: [
        "",
      ],
    },
    {
      employer: "California State University, Fullerton",
      title: "Assure-US Summer Research Peer Mentor",
      startDate: new Date(2023, 4),
      endDate: new Date(2023, 6),
      
      tasks: [
        ":D",       
      ],
      tags: [
        "",
      ],
    },
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
      employer: "Association for Computing Machinery, CSU-Fullerton",
      title: "Development Officer",
      startDate: new Date(2022, 3),
      endDate: new Date(2022, 7),
      tasks: [
        "Delivered weekly educational workshops to students on various topics such in web development, such as leveraging APIs and understanding HTTP",
        "Oversaw semester-long projects and offered technical advice to aid team members in completing their personal projects ",
       
      ],
      tags: ["Github", "Web Development",],
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


