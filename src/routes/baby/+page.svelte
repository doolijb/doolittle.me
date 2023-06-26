<script>
    import {metaStore} from '../../stores';
    import Icon from '@iconify/svelte';
    import { Avatar } from '@skeletonlabs/skeleton';
    import eveIcon from '../../assets/images/eve_icon.jpg'
    import w27_3d_1 from '../../assets/images/w27_3d_1.jpg'
    import w27_3d_2 from '../../assets/images/w27_3d_2.jpg'
    import w27_3d_3 from '../../assets/images/w27_3d_3.jpg'
    import w27_3d_4 from '../../assets/images/w27_3d_4.jpg'
    import w27_3d_5 from '../../assets/images/w27_3d_5.jpg'
    import w27_3d_6 from '../../assets/images/w27_3d_6.jpg' 
    export const prerender = true;

    $metaStore.title = 'Baby Shower';

    const qaData = [
		{ 
            question: "When is the baby due?", answers: [
                "We are expecting her by August 30th",
        ] },
        { 
            question: "Should we bring food or drinks?", answers: [
                "BBQ will be catered and beverages will be supplied for the event, but thank you for asking!"
            ]
        },
        {
            question: "Will there be alcohol?", answers: [
                "The actual party will be alcohol free, but there will be plenty of opportunity to celebrate in the evening!"
            ]
        },
		{ 
            question: "What items do you need the most?", answers: [
                "Diapers and wipes of all sizes",
                "Baby clothes 3, 6 months and up, especially cotton fabrics",
                "Assorted baby bottles, pacifiers, and teethers",
                "We keep our registry up to date with the single purchase items we need, or want the most"
            ] 
        },
        {
            question: "What items should we avoid buying?", answers: [
                "Blankets, newborn onesies, there's plenty of those already!",
                "Please no Johnson & Johnson products, we're trying to avoid those",
                "Jumpers and walkers",
            ]
        },
        {
            question: "Are second hand and thrift items okay?", answers: [
                "Absolutely! We love second hand items and are happy to receive them",
                "If the items are listed in the registry, please mark them as purchased"
            ]
        },
        {
            question: "What's the best way to get in touch with you?", answers: [
                "Text or email is the best way to reach us, please click the contact link above for more details"
            ]
        }
	];

    const w27Gallery = [w27_3d_1, w27_3d_2, w27_3d_3, w27_3d_4, w27_3d_5, w27_3d_6]
</script>

<p class="content-center text-center w-full my-3">
    <span class="inline-block">
        <Avatar src={eveIcon} width="w-32" rounded="rounded-full" />
        <small class="opacity-75">
            Last updated: 6/25/2023
        </small>
    </span>
</p>


<p>
Hello dear friends and family,
</p>
<p class="mt-3">
We're absolutely thrilled to announce that we're expecting our first baby girl in August! And what better way to celebrate than with the people we love and cherish?
</p>
<p class="mt-3">
So, put on your party hats and join us for a memorable baby shower on July 15th, in the beautiful city of Spokane. We are expecting to cater BBQ and are still planning for the time and venue.
</p>
<p class="mt-3">
    We will update this page as soon as we have more details. Please follow the link below to RSVP as soon as possible so we can plan accordingly.
</p>
<p class="mt-3">
Now, there's something we want you to know. Your presence at our baby shower is the most precious gift we could ask for. But if you'd like to bring a little something for our soon-to-arrive bundle of joy, we've put together a baby list that might help guide you. Please remember there's absolutely no obligation - your love and support mean the world to us!
</p>
<p class="mt-3">
Stay tuned for more details on the time and venue.
</p>
<p class="mt-3">
We can't wait to celebrate this wonderful milestone with all of you!
</p>
<p class="mt-6">
Warmest regards,
</p>
<p class="mt-3">
    <i>
        Jody & Tonya Doolittle
    </i>
</p>

<br class="mt-3">

<h3 class="h3">
    Links
</h3>

<ul class="ms-3">
    <li class="my-2">
        <a 
            href="https://docs.google.com/forms/d/1TwqAWzPlFo2dIQytiV4JzRi9_q0O7s8jFbNWDwRvQ1Y" 
            target="_blank" 
            class="btn variant-filled"
        >
            RSVP and get notifications
            <Icon icon="gg:external" class="inline-block w-5 h-5 ms-2" />
        </a>
    </li>
    <li class="my-2">
        <a 
            href="https://www.babylist.com/list/tonya-doolittle-registry" 
            target="_blank" 
            class="btn variant-filled"
        >
            Registry at BabyList.com 
            <Icon icon="gg:external" class="inline-block w-5 h-5 ms-2" />
        </a>
    </li>
    <li class="my-2">
        <a 
            href="https://calendar.google.com/calendar/event?action=TEMPLATE&tmeid=Mzhydms1OTJicGVsamdiaG1paGhxN281aXYgZG9vbGlqYkBt&tmsrc=doolijb%40gmail.com"
            target="_blank"
            class="btn variant-filled"
        >
            Add to Google Calendar
            <Icon icon="gg:external" class="inline-block w-5 h-5 ms-2" />
    </a>
    </li>
    <li class="my-2">
        <a 
            href="/contact" 
            class="btn variant-filled"
        >
            Contact us
        </a>
    </li>
</ul>


<br class="mt-3">

<h3 class="h3">
    Event
</h3>
    <p class="mt-2">
        <b>Date:</b> July 15th, 2023
    </p>
    <p>
        <b>Time:</b> TBD
    </p>
    <p>
        <b class="mt-2">City:</b> Spokane, WA
    </p>
    <p>
        <b class="mt-2">Venue:</b> TBD
    </p>
    
<br class="mt-3">

<h3 class="h3">
    FAQ
</h3> 

<dl class="relative">
    {#each qaData as v, i}
        <div class="my-3">
            <div class="flex">
                <span class="badge-icon p-4 variant-soft-primary me-3">{i + 1}</span>
                <span class="mt-1">
                    <b>
                        {v.question}
                    </b>
                </span>
            </div>
            {#each v.answers as answer}
                <div class="opacity-75 relative ms-2">
                    <Icon icon="mdi:dot" class="inline-block w-5 h-5 me-2" />
                    <span>
                        {answer}
                    </span>
                </div>
            {/each}
        </div>
    {/each}
</dl>


<br class="mt-3">

<h3 class="h3">
    Week 27 Gallery
</h3> 

<div class="mt-3 grid grid-cols-1 md:grid-cols-2 gap-4 w-full">
    {#each w27Gallery as v, i}
        <img src={v} class="cols-12 rounded-lg" />
    {/each}
</div>