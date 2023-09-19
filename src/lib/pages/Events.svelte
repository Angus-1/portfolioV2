<script lang="ts">
    import Card from "$lib/components/Card.svelte";
    import Page from "$lib/components/Page.svelte";
    import { neutralBackground } from "$lib/utils/constants";
  
    type Event = {
      event: string;
      title: string;
      date: Date;
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
      return `${months[date.getMonth()-1]} ${date.getFullYear()}`;
    }
    function formatDateString(formatVar: Date) {
      return `${dateToString(formatVar)}`;
    }
    const jobs: Array<Event> = [
      {
        event: "International Collegiate Programming Contest ",
        title: "SoCal Region competitor",
        date: new Date(2023, 2),
        tasks: [
          "Utilized skills in algorithms, data structures, and teamwork to compete against other universities in the SoCal area",
          "Overcame challenges such as time constraints and unfamiliar problem sets",
        ],
        tags: [
          "Competitive Programming",
        ],
      },
      {
        event: "LA Hacks 2023", 
        title: "Participant", 
        date: new Date(2023, 4),  
        tasks: ["Developed a web application over 24 hours to output information on a location search input. This includes popular attractions, historical summary and geographical summary.",],
        tags: ["Hackathon",],
      },
      {
        event: "Fully Hacks 2023", 
        title: "Operations Manager", 
        date: new Date(2023, 4),  
        tasks: ["Oversee the logistical and organizational aspects of FullyHacks, a hackathon event at CSUF with over 200 students",
        "Initiate and maintain communication with potential sponsors for FullyHacks, leveraging networking skills to secure sponsorships and support for the events from companies, including Redbull, Celsius, Wolfram, .xyz domains, Stickermule, Balsamiq, Prisma, Echo3D and Digital Ocean "
    
    ],
        tags: ["Security Conference",],
      }, {
        event: "DEFCON 31", 
        title: "attendee", 
        date: new Date(2023, 8),  
        tasks: ["Had a great time learning about security!",
    
    ],
        tags: ["Security Conference",],
      },     {
        event: "Converge Security Conference", 
        title: "attendee", 
        date: new Date(2023, 9),  
        tasks: ["Got insight into cyber, physical, and operational security domains",
    
    ],
        tags:  ["Security Conference",],
      },    
   
    ];
  
    export let backgroundClass = neutralBackground;
  </script>
  
  <Page id="events" title="Events attended" {backgroundClass}>
    <div
      class="container mx-auto grid max-w-screen-xl gap-4 md:grid-cols-1 xl:grid-cols-2 3xl:grid-cols-4"
    >
      {#each jobs as event}
        <Card
          title={event.event}
          subtitle={`${event.title}, ${formatDateString(event.date)}`}
          tags={event.tags}
        >
          {#if event.description}
            <div class="mb-1">
              {event.description ?? ""}
            </div>
          {/if}
          <ul class="list-disc list-inside">
            {#each event.tasks as task}
              <li>{task}</li>
            {/each}
          </ul>
        </Card>
      {/each}
    </div>
  </Page>
  
  
  