<template>
    <div class="pl-5">
        <a :href="url"><img :src="img" width="100%"></a>
    </div>
    
</template>

<script>
import LinkedInImg from "~/assets/linkedin.svg"
import GithubImg from "~/assets/github.svg"
import TwitterImg from "~/assets/twitter.svg"
export default {
    name: 'SocialIcon',
    props: ["url"],
    computed: {
        img: function() {
            let domain = (new URL(this.url));
            switch (domain.hostname) {
                case "linkedin.com":
                    return LinkedInImg
                case "twitter.com":
                    return TwitterImg              
                case "github.com":
                    return GithubImg
                default:
                    return ""
            }
        }
    }
}
</script>