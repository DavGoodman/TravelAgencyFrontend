<template>
    <div class="post">
        <div class="post-row">
            <span class="post-label">
                {{ post.travelAgent ? "Travel Agent: " : "Guest: "}} 
            </span> 
            <span class="post-content">
                {{ post.travelAgent ? post.travelAgent : post.guestName  }}
            </span>
        </div>

        <div class="post-row">
            <span class="post-label"> 
                {{ post.travelAgent ? "Total Nights: " : "Total Observations: "}}
            </span> 
            <span class="post-content">
                {{ post.travelAgent ? post.totalNumberOfNights : post.totalObservations  }}
            </span>
           
        </div>
    </div>
</template>

<script>

export default {
    props: ['post']
}

</script>