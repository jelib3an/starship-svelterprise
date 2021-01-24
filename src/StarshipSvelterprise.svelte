<script>
  import { derived } from 'svelte/store';
  import { maxWarpFactor, warpFactor } from './WarpControls.svelte';

  const defaultShipClass = 'ambassador';
  const availableShipClasses = ['ambassador', 'galaxy'];

  export let shipClass = defaultShipClass;
  if (!availableShipClasses.includes(shipClass)) {
    shipClass = defaultShipClass;
  }

  const quote = derived(warpFactor, ($warpFactor) => {
    if ($warpFactor >= maxWarpFactor) {
      return "I'm giving her all she's got, captain!";
    }
    return 'Boldly go where no man has gone before!';
  });

  const position = { x: 200, y: 75 };
  function navigate(e) {
    let x;
    let y;
    switch (e.keyCode) {
      case 37:
        x = position.x - 10;
        break; // left
      case 38:
        y = position.y - 10;
        break; // up
      case 39:
        x = position.x + 10;
        break; // right
      case 40:
        y = position.y + 10;
        break; // down
      default:
        return;
    }

    if (x > 0 && x < 400) {
      position.x = x;
    }

    if (y > 0 && y < 170) {
      position.y = y;
    }
  }

  let maneuvers = -1;
  $: position && maneuvers++;
</script>

<div class="quote">
  <slot>
    <p>{$quote}</p>
  </slot>
</div>
<div class="starfield" tabindex="0" on:keydown|preventDefault={navigate}>
  <div class="sm-stars" style="animation-duration:{25 / $warpFactor}s;" />
  <div class="med-stars" style="animation-duration:{50 / $warpFactor}s;" />
  <div class="lg-stars" style="animation-duration:{75 / $warpFactor}s;" />
  <div style="position:relative; left:{position.x}px; top:{position.y}px;">
    <img src="{shipClass}-class.png" alt="starship" />
  </div>
</div>
<div class="maneuvers">
  <p>(Click ship, use arrow keys) Evasive maneuvers: {maneuvers}</p>
</div>

<style>
  .quote {
    font-family: 'Times New Roman', Times, serif;
    font-style: italic;
    text-align: center;
  }

  .maneuvers {
    width: 500px;
    margin: auto;
    text-align: right;
    font-size: 11px;
  }

  .starfield {
    /* create visible canvas 500 x 200 */
    width: 500px;
    height: 200px;
    background: radial-gradient(ellipse at bottom, #1b2735 0%, #090a0f 100%);
    overflow: hidden;
    outline: none;
    margin: 5px auto 5px auto;
  }

  /* Randomly plot stars within 1000 x 200 area (double the width of visible canvas) */
  .sm-stars,
  .sm-stars:after {
    width: 1px;
    height: 1px;
    background: transparent;
    box-shadow: 352px 33px #fff, 219px 49px #fff, 202px 126px #fff, 391px 185px #fff, 97px 28px #fff,
      637px 135px #fff, 911px 46px #fff, 60px 118px #fff, 862px 16px #fff, 535px 127px #fff,
      366px 125px #fff, 968px 165px #fff, 604px 49px #fff, 422px 11px #fff, 548px 22px #fff,
      711px 64px #fff, 732px 48px #fff, 88px 77px #fff, 991px 52px #fff, 758px 136px #fff,
      324px 188px #fff, 837px 20px #fff, 150px 34px #fff, 152px 150px #fff, 328px 31px #fff,
      297px 40px #fff, 134px 39px #fff, 617px 121px #fff, 368px 145px #fff, 590px 16px #fff,
      314px 152px #fff, 309px 63px #fff, 586px 129px #fff, 626px 196px #fff, 932px 97px #fff,
      609px 91px #fff, 774px 20px #fff, 874px 133px #fff, 699px 61px #fff, 37px 78px #fff,
      946px 63px #fff, 459px 137px #fff, 268px 62px #fff, 180px 115px #fff, 633px 147px #fff,
      71px 33px #fff, 868px 160px #fff, 450px 65px #fff, 330px 67px #fff, 920px 13px #fff,
      791px 128px #fff, 46px 135px #fff, 797px 175px #fff, 353px 75px #fff, 941px 182px #fff,
      321px 69px #fff, 983px 119px #fff, 574px 169px #fff, 578px 36px #fff, 497px 170px #fff,
      614px 145px #fff, 447px 180px #fff, 247px 35px #fff, 392px 148px #fff, 3px 43px #fff,
      482px 42px #fff, 987px 21px #fff, 523px 139px #fff, 167px 67px #fff, 475px 88px #fff,
      740px 178px #fff, 503px 103px #fff, 67px 163px #fff, 507px 192px #fff, 611px 47px #fff,
      401px 62px #fff, 250px 36px #fff, 190px 91px #fff, 900px 196px #fff, 284px 162px #fff,
      852px 93px #fff, 559px 118px #fff, 565px 57px #fff, 92px 74px #fff, 311px 165px #fff,
      579px 26px #fff, 546px 74px #fff, 917px 153px #fff, 483px 72px #fff, 90px 65px #fff,
      671px 66px #fff, 270px 140px #fff, 457px 135px #fff, 670px 42px #fff, 390px 72px #fff,
      109px 73px #fff, 187px 81px #fff, 378px 177px #fff, 133px 11px #fff, 470px 190px #fff,
      358px 41px #fff, 483px 196px #fff, 982px 24px #fff, 325px 111px #fff, 461px 141px #fff,
      154px 99px #fff, 228px 22px #fff, 173px 30px #fff, 577px 76px #fff, 468px 124px #fff,
      799px 100px #fff, 824px 140px #fff, 966px 85px #fff, 234px 61px #fff, 73px 130px #fff,
      294px 95px #fff, 600px 126px #fff, 455px 132px #fff, 846px 133px #fff, 526px 63px #fff,
      393px 39px #fff, 682px 168px #fff, 254px 151px #fff, 962px 51px #fff, 643px 123px #fff,
      552px 154px #fff, 751px 181px #fff, 507px 44px #fff, 123px 6px #fff, 850px 110px #fff,
      788px 26px #fff, 820px 55px #fff, 128px 82px #fff, 59px 159px #fff, 215px 114px #fff,
      742px 124px #fff, 925px 133px #fff, 182px 136px #fff, 227px 9px #fff, 473px 166px #fff,
      834px 97px #fff, 737px 119px #fff, 571px 118px #fff, 635px 110px #fff, 505px 150px #fff,
      879px 160px #fff, 547px 42px #fff, 324px 178px #fff, 142px 86px #fff, 225px 43px #fff;
  }

  .med-stars,
  .med-stars:after {
    width: 2px;
    height: 2px;
    background: transparent;
    box-shadow: 633px 99px #fff, 423px 130px #fff, 768px 119px #fff, 944px 147px #fff,
      763px 132px #fff, 401px 140px #fff, 970px 115px #fff, 502px 3px #fff, 192px 75px #fff,
      808px 31px #fff, 470px 151px #fff, 671px 122px #fff, 463px 195px #fff, 793px 90px #fff,
      950px 76px #fff, 184px 158px #fff, 819px 36px #fff, 252px 192px #fff, 237px 199px #fff,
      242px 44px #fff, 64px 162px #fff, 268px 115px #fff, 915px 11px #fff, 548px 91px #fff,
      384px 52px #fff, 950px 94px #fff, 996px 122px #fff, 514px 115px #fff, 32px 10px #fff,
      455px 192px #fff, 239px 73px #fff, 111px 9px #fff, 621px 120px #fff, 188px 148px #fff,
      91px 3px #fff, 234px 161px #fff, 554px 183px #fff, 573px 84px #fff, 563px 34px #fff,
      248px 81px #fff, 524px 161px #fff, 809px 137px #fff, 722px 17px #fff, 437px 15px #fff,
      388px 71px #fff, 419px 149px #fff, 14px 62px #fff, 678px 68px #fff, 934px 28px #fff,
      558px 1px #fff;
  }

  .lg-stars,
  .lg-stars:after {
    width: 3px;
    height: 3px;
    background: transparent;
    box-shadow: 663px 181px #fff, 946px 120px #fff, 263px 46px #fff, 615px 187px #fff,
      399px 11px #fff, 843px 141px #fff, 983px 7px #fff, 809px 73px #fff, 27px 3px #fff,
      37px 22px #fff, 367px 60px #fff, 965px 33px #fff, 740px 124px #fff, 675px 192px #fff,
      631px 13px #fff, 601px 138px #fff, 632px 188px #fff, 480px 17px #fff, 500px 30px #fff,
      871px 45px #fff;
  }

  /* Animate the stars towards the left. When complete, reset positions 1000px to the right. */
  @keyframes moveLeft {
    from {
      transform: translateX(0px);
    }
    to {
      transform: translateX(-1000px);
    }
  }

  .sm-stars,
  .med-stars,
  .lg-stars {
    animation: moveLeft linear infinite;
  }

  .sm-stars:after,
  .med-stars:after,
  .lg-stars:after {
    content: ' ';
    position: absolute;
    left: 1000px;
  }
</style>
