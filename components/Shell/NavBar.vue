<template>
    <nav class="navBar__navigation">
        <ul class="navBar__list">
            <li>
                <NuxtLink to="NewsArticles">
                    News & Articles 
                </NuxtLink>
            </li>
            <li>
                <NuxtLink to="Events">
                    Events 
                </NuxtLink>
            </li>
            <li>
                <NuxtLink to="IndustryCareers">
                    Industry Careers 
                </NuxtLink>
            </li>
            <li>
                <NuxtLink to="Advertising">
                    Advertising 
                </NuxtLink>
            </li>
            <li>
                <NuxtLink to="Company">
                    Company 
                </NuxtLink>
            </li>
        </ul>
        <div class="navBar__login-items">
            <!-- Search Icon Component -->
            <SignUp class="navBar__login-item" />
            <!-- LOG IN Component --> 
            Log In 
        </div>
    </nav>
</template>

<script>
import SignUp from './Navigation/SignUp.vue'

export default {
    components: {
        SignUp,
    }
}
</script>


<style lang="scss">
    .navBar__navigation {
        padding: 20px 30px;
        display: flex;
        justify-content: space-between;
    }

    .navBar__list {
        display: flex;
        @include unordered-list;

        li {
            padding: 0 15px;

            a {
                color: $bisnow-charcoal;
                font-size: 14px;
                text-decoration: none;
            }
        }
    }

    .navBar__login-items {
        display: flex;
        align-items: center;
    }

    .navBar__login-item {
        margin: 0 10px;
    }

</style>