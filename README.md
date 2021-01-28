C# Theater Internship

Introduction:

During my Prosper IT Consulting internship, I was part of a two week sprint working with a team of developers to maintain and build a content website for Vertigo Theater Company. The team was working on developing a full scale MVC Web Application in C#/.Net. Working with Azure DevOps to ensure steady workflow and team management created a professional coding environment. I saw how a good developer works in a team building piece by piece for the final product. I worked on front end and back end stories improving styling or working with data. Over the two week sprint, I gained experience in AGILE/SCRUM methods and am confident I will use all these skills on future projects. 

![Theaterimage](/theater2.PNG?raw=true "Optional Title")  

Rental Model: 

I created a Rental model that represents the physical items or rooms that a User can rent. I created a one to many relationship between the RentalRequest table and the Rental table.

        public class Rental
        {
                [Key]
                public int RentalId { get; set; }

                [Display(Name = "Rental Name")]
                public string RentalName { get; set; }
                [Display(Name = "Rental Cost")]
                public int RentalCost { get; set; }
                public string RentalHistory { get; set; } // temporarily string but needs to be <List>RentalHistory once class is made
                [Display(Name = "Flaws And Damages")]
                public string FlawsAndDamages { get; set; }

                public int RentalRequestId { get; set; }
                public RentalRequest RentalRequest { get; set; }
        }
        
        
        
Rental Request Model:

I created a Rentel Request model that represents when a company or individual would like to rent a room or equipment at the theatre. I used DateTime to find time of rental created and duration and implemented two methods GetRentalDuration() and GetTimeRemaining(). 

        public class RentalRequest
        {
                public RentalRequest()
                {
                        RequestedTime = DateTime.Now;
                }

                [Key] //Primary Key
                public int RentalRequestId { get; set; }

                [Display(Name = "Contact Person")]
                public string ContactPerson { get; set; }
                public string Company { get; set; }
                [Display(Name = "Requested Time")]
                public DateTime RequestedTime { get; set; }
                [Display(Name = "Start Time")]
                public DateTime StartTime { get; set; }
                [Display(Name = "End Time")]
                public DateTime EndTime { get; set; }
                [Display(Name = "Project Info")]
                public string ProjectInfo { get; set; }
                public List<Rental> Rentals { get; set; } //Changed property from string Requests to List<Rental> Rentals
                [Display(Name = "Rental Code")]
                public int RentalCode { get; set; }
                public bool Accepted { get; set; }
                [Display(Name = "Contract Signed")]
                public bool ContractSigned { get; set; }

                public TimeSpan GetRentalDuration()
                {
                        TimeSpan duration = EndTime - StartTime;
                        return duration;
                }

                public TimeSpan GetTimeRemaining()
                {
                        TimeSpan duration = DateTime.Now - EndTime;
                        return duration;
                }
        }

![Theaterimage](/theater.PNG?raw=true "Optional Title")      

Front End:

Fixed spacing and width issues with Award Preview Card. Created CSS class to resolve issue with navbar and top margin placement. 

.awardPreview {
    max-width: 600px;
    top: 65px;
}

<div class="card awardPreview bg-black border border-light mx-auto sticky-top">
        <div class="card-body">
                < Removed line breaks in Award Preview Card -->
                < <br><br /> -->








Working in a group of developers on all aspects of the project like front end, back end, and management showed me how a project can come together piece by piece. The AGILE/SCRUM daily meetings taught me experience in team communication. Azure Devops experience was valuable. 
