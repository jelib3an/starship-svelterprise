<script>
  let speed = 1;
</script>

<div class="enterprise-container">
  <div class="sm-stars" style="animation-duration:{1/speed * 25}s"></div>
  <div class="med-stars" style="animation-duration:{1/speed * 50}s"></div>
  <div class="lg-stars" style="animation-duration:{1/speed * 75}s"></div>
</div>

<style>
 .enterprise-container {
    margin: auto;
    width: 500px;
    height: 200px;
    background: radial-gradient(ellipse at bottom, #1b2735 0%, #090a0f 100%);
    overflow: hidden;
  }

  @keyframes starfield {
    from {
      transform: translateX(0px);
    }
    to {
      transform: translateX(-500px);
    }
  }

  .sm-stars {
    width: 1px;
    height: 1px;
    background: transparent;
    box-shadow: 352px 33px #FFF , 219px 49px #FFF , 202px 126px #FFF , 391px 185px #FFF , 97px 28px #FFF , 637px 135px #FFF , 911px 46px #FFF , 60px 118px #FFF , 862px 16px #FFF , 535px 127px #FFF , 366px 125px #FFF , 968px 165px #FFF , 604px 49px #FFF , 422px 11px #FFF , 548px 22px #FFF , 711px 64px #FFF , 732px 48px #FFF , 88px 77px #FFF , 991px 52px #FFF , 758px 136px #FFF , 324px 188px #FFF , 837px 20px #FFF , 150px 34px #FFF , 152px 150px #FFF , 328px 31px #FFF , 297px 40px #FFF , 134px 39px #FFF , 617px 121px #FFF , 368px 145px #FFF , 590px 16px #FFF , 314px 152px #FFF , 309px 63px #FFF , 586px 129px #FFF , 626px 196px #FFF , 932px 97px #FFF , 609px 91px #FFF , 774px 20px #FFF , 874px 133px #FFF , 699px 61px #FFF , 37px 78px #FFF , 946px 63px #FFF , 459px 137px #FFF , 268px 62px #FFF , 180px 115px #FFF , 633px 147px #FFF , 71px 33px #FFF , 868px 160px #FFF , 450px 65px #FFF , 330px 67px #FFF , 920px 13px #FFF , 791px 128px #FFF , 46px 135px #FFF , 797px 175px #FFF , 353px 75px #FFF , 941px 182px #FFF , 321px 69px #FFF , 983px 119px #FFF , 574px 169px #FFF , 578px 36px #FFF , 497px 170px #FFF , 614px 145px #FFF , 447px 180px #FFF , 247px 35px #FFF , 392px 148px #FFF , 3px 43px #FFF , 482px 42px #FFF , 987px 21px #FFF , 523px 139px #FFF , 167px 67px #FFF , 475px 88px #FFF , 740px 178px #FFF , 503px 103px #FFF , 67px 163px #FFF , 507px 192px #FFF , 611px 47px #FFF , 401px 62px #FFF , 250px 36px #FFF , 190px 91px #FFF , 900px 196px #FFF , 284px 162px #FFF , 852px 93px #FFF , 559px 118px #FFF , 565px 57px #FFF , 92px 74px #FFF , 311px 165px #FFF , 579px 26px #FFF , 546px 74px #FFF , 917px 153px #FFF , 483px 72px #FFF , 90px 65px #FFF , 671px 66px #FFF , 270px 140px #FFF , 457px 135px #FFF , 670px 42px #FFF , 390px 72px #FFF , 109px 73px #FFF , 187px 81px #FFF , 378px 177px #FFF , 133px 11px #FFF , 470px 190px #FFF , 358px 41px #FFF , 483px 196px #FFF , 982px 24px #FFF , 325px 111px #FFF , 461px 141px #FFF , 154px 99px #FFF , 228px 22px #FFF , 173px 30px #FFF , 577px 76px #FFF , 468px 124px #FFF , 799px 100px #FFF , 824px 140px #FFF , 966px 85px #FFF , 234px 61px #FFF , 73px 130px #FFF , 294px 95px #FFF , 600px 126px #FFF , 455px 132px #FFF , 846px 133px #FFF , 526px 63px #FFF , 393px 39px #FFF , 682px 168px #FFF , 254px 151px #FFF , 962px 51px #FFF , 643px 123px #FFF , 552px 154px #FFF , 751px 181px #FFF , 507px 44px #FFF , 123px 6px #FFF , 850px 110px #FFF , 788px 26px #FFF , 820px 55px #FFF , 128px 82px #FFF , 59px 159px #FFF , 215px 114px #FFF , 742px 124px #FFF , 925px 133px #FFF , 182px 136px #FFF , 227px 9px #FFF , 473px 166px #FFF , 834px 97px #FFF , 737px 119px #FFF , 571px 118px #FFF , 635px 110px #FFF , 505px 150px #FFF , 879px 160px #FFF , 547px 42px #FFF , 324px 178px #FFF , 142px 86px #FFF , 225px 43px #FFF;
    animation: starfield linear infinite;
  }
  .sm-stars:after {
    content: " ";
    position: absolute;
    top: 200px;
    width: 1px;
    height: 1px;
    background: transparent;
    box-shadow: 352px 33px #FFF , 219px 49px #FFF , 202px 126px #FFF , 391px 185px #FFF , 97px 28px #FFF , 637px 135px #FFF , 911px 46px #FFF , 60px 118px #FFF , 862px 16px #FFF , 535px 127px #FFF , 366px 125px #FFF , 968px 165px #FFF , 604px 49px #FFF , 422px 11px #FFF , 548px 22px #FFF , 711px 64px #FFF , 732px 48px #FFF , 88px 77px #FFF , 991px 52px #FFF , 758px 136px #FFF , 324px 188px #FFF , 837px 20px #FFF , 150px 34px #FFF , 152px 150px #FFF , 328px 31px #FFF , 297px 40px #FFF , 134px 39px #FFF , 617px 121px #FFF , 368px 145px #FFF , 590px 16px #FFF , 314px 152px #FFF , 309px 63px #FFF , 586px 129px #FFF , 626px 196px #FFF , 932px 97px #FFF , 609px 91px #FFF , 774px 20px #FFF , 874px 133px #FFF , 699px 61px #FFF , 37px 78px #FFF , 946px 63px #FFF , 459px 137px #FFF , 268px 62px #FFF , 180px 115px #FFF , 633px 147px #FFF , 71px 33px #FFF , 868px 160px #FFF , 450px 65px #FFF , 330px 67px #FFF , 920px 13px #FFF , 791px 128px #FFF , 46px 135px #FFF , 797px 175px #FFF , 353px 75px #FFF , 941px 182px #FFF , 321px 69px #FFF , 983px 119px #FFF , 574px 169px #FFF , 578px 36px #FFF , 497px 170px #FFF , 614px 145px #FFF , 447px 180px #FFF , 247px 35px #FFF , 392px 148px #FFF , 3px 43px #FFF , 482px 42px #FFF , 987px 21px #FFF , 523px 139px #FFF , 167px 67px #FFF , 475px 88px #FFF , 740px 178px #FFF , 503px 103px #FFF , 67px 163px #FFF , 507px 192px #FFF , 611px 47px #FFF , 401px 62px #FFF , 250px 36px #FFF , 190px 91px #FFF , 900px 196px #FFF , 284px 162px #FFF , 852px 93px #FFF , 559px 118px #FFF , 565px 57px #FFF , 92px 74px #FFF , 311px 165px #FFF , 579px 26px #FFF , 546px 74px #FFF , 917px 153px #FFF , 483px 72px #FFF , 90px 65px #FFF , 671px 66px #FFF , 270px 140px #FFF , 457px 135px #FFF , 670px 42px #FFF , 390px 72px #FFF , 109px 73px #FFF , 187px 81px #FFF , 378px 177px #FFF , 133px 11px #FFF , 470px 190px #FFF , 358px 41px #FFF , 483px 196px #FFF , 982px 24px #FFF , 325px 111px #FFF , 461px 141px #FFF , 154px 99px #FFF , 228px 22px #FFF , 173px 30px #FFF , 577px 76px #FFF , 468px 124px #FFF , 799px 100px #FFF , 824px 140px #FFF , 966px 85px #FFF , 234px 61px #FFF , 73px 130px #FFF , 294px 95px #FFF , 600px 126px #FFF , 455px 132px #FFF , 846px 133px #FFF , 526px 63px #FFF , 393px 39px #FFF , 682px 168px #FFF , 254px 151px #FFF , 962px 51px #FFF , 643px 123px #FFF , 552px 154px #FFF , 751px 181px #FFF , 507px 44px #FFF , 123px 6px #FFF , 850px 110px #FFF , 788px 26px #FFF , 820px 55px #FFF , 128px 82px #FFF , 59px 159px #FFF , 215px 114px #FFF , 742px 124px #FFF , 925px 133px #FFF , 182px 136px #FFF , 227px 9px #FFF , 473px 166px #FFF , 834px 97px #FFF , 737px 119px #FFF , 571px 118px #FFF , 635px 110px #FFF , 505px 150px #FFF , 879px 160px #FFF , 547px 42px #FFF , 324px 178px #FFF , 142px 86px #FFF , 225px 43px #FFF;
  }

  .med-stars {
    width: 2px;
    height: 2px;
    background: transparent;
    box-shadow: 633px 99px #FFF , 423px 130px #FFF , 768px 119px #FFF , 944px 147px #FFF , 763px 132px #FFF , 401px 140px #FFF , 970px 115px #FFF , 502px 3px #FFF , 192px 75px #FFF , 808px 31px #FFF , 470px 151px #FFF , 671px 122px #FFF , 463px 195px #FFF , 793px 90px #FFF , 950px 76px #FFF , 184px 158px #FFF , 819px 36px #FFF , 252px 192px #FFF , 237px 199px #FFF , 242px 44px #FFF , 64px 162px #FFF , 268px 115px #FFF , 915px 11px #FFF , 548px 91px #FFF , 384px 52px #FFF , 950px 94px #FFF , 996px 122px #FFF , 514px 115px #FFF , 32px 10px #FFF , 455px 192px #FFF , 239px 73px #FFF , 111px 9px #FFF , 621px 120px #FFF , 188px 148px #FFF , 91px 3px #FFF , 234px 161px #FFF , 554px 183px #FFF , 573px 84px #FFF , 563px 34px #FFF , 248px 81px #FFF , 524px 161px #FFF , 809px 137px #FFF , 722px 17px #FFF , 437px 15px #FFF , 388px 71px #FFF , 419px 149px #FFF , 14px 62px #FFF , 678px 68px #FFF , 934px 28px #FFF , 558px 1px #FFF;
    animation: starfield linear infinite;
  }
  .med-stars:after {
    content: " ";
    position: absolute;
    top: 200px;
    width: 2px;
    height: 2px;
    background: transparent;
    box-shadow: 633px 99px #FFF , 423px 130px #FFF , 768px 119px #FFF , 944px 147px #FFF , 763px 132px #FFF , 401px 140px #FFF , 970px 115px #FFF , 502px 3px #FFF , 192px 75px #FFF , 808px 31px #FFF , 470px 151px #FFF , 671px 122px #FFF , 463px 195px #FFF , 793px 90px #FFF , 950px 76px #FFF , 184px 158px #FFF , 819px 36px #FFF , 252px 192px #FFF , 237px 199px #FFF , 242px 44px #FFF , 64px 162px #FFF , 268px 115px #FFF , 915px 11px #FFF , 548px 91px #FFF , 384px 52px #FFF , 950px 94px #FFF , 996px 122px #FFF , 514px 115px #FFF , 32px 10px #FFF , 455px 192px #FFF , 239px 73px #FFF , 111px 9px #FFF , 621px 120px #FFF , 188px 148px #FFF , 91px 3px #FFF , 234px 161px #FFF , 554px 183px #FFF , 573px 84px #FFF , 563px 34px #FFF , 248px 81px #FFF , 524px 161px #FFF , 809px 137px #FFF , 722px 17px #FFF , 437px 15px #FFF , 388px 71px #FFF , 419px 149px #FFF , 14px 62px #FFF , 678px 68px #FFF , 934px 28px #FFF , 558px 1px #FFF;
  }

  .lg-stars {
    width: 3px;
    height: 3px;
    background: transparent;
    box-shadow: 663px 181px #FFF , 946px 120px #FFF , 263px 46px #FFF , 615px 187px #FFF , 399px 11px #FFF , 843px 141px #FFF , 983px 7px #FFF , 809px 73px #FFF , 27px 3px #FFF , 37px 22px #FFF , 367px 60px #FFF , 965px 33px #FFF , 740px 124px #FFF , 675px 192px #FFF , 631px 13px #FFF , 601px 138px #FFF , 632px 188px #FFF , 480px 17px #FFF , 500px 30px #FFF , 871px 45px #FFF;
    animation: starfield linear infinite;
  }
  .lg-stars:after {
    content: " ";
    position: absolute;
    top: 200px;
    width: 3px;
    height: 3px;
    background: transparent;
    box-shadow: 663px 181px #FFF , 946px 120px #FFF , 263px 46px #FFF , 615px 187px #FFF , 399px 11px #FFF , 843px 141px #FFF , 983px 7px #FFF , 809px 73px #FFF , 27px 3px #FFF , 37px 22px #FFF , 367px 60px #FFF , 965px 33px #FFF , 740px 124px #FFF , 675px 192px #FFF , 631px 13px #FFF , 601px 138px #FFF , 632px 188px #FFF , 480px 17px #FFF , 500px 30px #FFF , 871px 45px #FFF;
  }
</style>