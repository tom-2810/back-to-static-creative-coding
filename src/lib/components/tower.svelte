<div class="tower">
    <div class="floor" />
    <div class="floor" />
    <div class="floor" />
    <div class="floor" />
    <div class="floor" />
    <div class="floor" />
    <div class="floor" />
    <div class="floor" />
    <div class="floor" />
    <div class="floor" />
    <div class="floor" />
    <div class="floor" />
    <div class="floor" />
    <div class="floor" />
    <div class="floor" />
    <div class="floor" />
</div>

<style>
    .tower {
        position: relative;
        top: -5rem;
        height: 250px;
        width: 250px;
        perspective: 300px;
    }

    .floor {
        position: absolute;
        border: 3px solid white;
        transform-style: preserve-3d;
        transform: rotateX(80deg);
        height: 100%;
        width: 100%;
        animation: 1s fold-out forwards;
        animation-delay: 1s;
    }

    .floor:hover {
        border-color: rgb(255, 0, 187);
    }

    .floor:nth-child(1n) {
        top: 0;
    }

    .floor:nth-child(2n) {
        top: 10px;
    }

    .floor:nth-child(3n) {
        top: 20px;
    }

    .floor:nth-child(4n) {
        top: 30px;
    }

    .floor:nth-child(5n) {
        top: 40px;
    }

    .floor:nth-child(6n) {
        top: 50px;
    }

    .floor:nth-child(7n) {
        top: 60px;
    }

    .floor:nth-child(8n) {
        top: 70px;
    }

    .floor:nth-child(9n) {
        top: 80px;
    }

    .floor:nth-child(10n) {
        top: 90px;
    }

    .floor:nth-child(11n) {
        top: 100px;
        opacity: 0.9;
    }

    .floor:nth-child(12n) {
        top: 110px;
        opacity: 0.75;
    }

    .floor:nth-child(13n) {
        top: 120px;
        opacity: 0.6;
    }

    .floor:nth-child(14n) {
        top: 130px;
        opacity: 0.45;
    }

    .floor:nth-child(15n) {
        top: 140px;
        opacity: 0.3;
    }

    .floor:nth-child(16n) {
        top: 150px;
        opacity: 0.15;
    }

    @keyframes fold-out {
        from {
            top: 0;
        }
    }
</style>
