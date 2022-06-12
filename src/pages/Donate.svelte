<script>
    import DonateForm from "../components/DonateForm.svelte";
    import TitleBar from "../components/TitleBar.svelte";
    import MainNavigator from "../components/MainNavigator.svelte";
    import DonationMap from "../components/DonationMap.svelte";

    let donationMap = null;

    function donationMade(event) {
        donationMap.addDonationMarker(event.detail.donation);
    }
</script>

<div class="columns is-vcentered">
    <div class="column is-two-thirds">
        <TitleBar subTitle={"Please make a Donation"} title={"Donation Services Inc."}/>
    </div>
    <div class="column">
        <MainNavigator/>
    </div>
</div>

<div class="columns is-vcentered">
    <div class="column has-text-centered">
        <DonationMap bind:this={donationMap}/>
    </div>
    <div class="column box has-text-centered">
        <h1 class="title is-4">Give Generously!</h1>
        <DonateForm on:message={donationMade}/>
    </div>
</div>