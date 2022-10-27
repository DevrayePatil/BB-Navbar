<script>
  import { getContext } from "svelte";
  import Icon from "svelte-icon";

  import MBCLogo from "./resources/new-mbc-logo.svg";

  import videoCamera from "./resources/video-camera.svg";
  import requestForDemo from "./resources/request-for-demo.svg";
  import writeToUs from "./resources/write-to-us.svg";
  import whatsApp from "./resources/whatsapp.svg";

  import myProfile from "./resources/my-profile.svg";
  import logout from "./resources/logout.svg";

  export let bgColor, title;
  export let option1, option2, option3;
  export let subOption1, subOption2, subOption3, subOption4;
  export let accountName, expiryMassage, userName;
  export let buttonText;
  export let onLogout;

  export let subOption1Link, subOption2Link, subOption3Link, subOption4Link;
  export let myProfileLink;

  const { styleable } = getContext("sdk");
  const component = getContext("component");
</script>

<div use:styleable={$component.styles}>
  <div class="nav-bar" style="--bg-color: {bgColor}">
    <span class="image-style">
      <Icon data={MBCLogo} size="60px" />
    </span>

    <div class="containt-style">
      <div>
        <div class="list-style">
          <ul>
            <li>{option1}</li>
            <li>{option2}</li>
            <li>
              {option3}
              <i class="arrow down" />
              <div class="sub-list-style">
                <ul>
                  <li>
                    <a href={subOption1Link} rel="noreferrer" target="_blank">
                    <span class="list-icon">
                      <Icon data={videoCamera} />
                    </span>
                    <span class="list-label">{subOption1}</span>
                  </a>
                  </li>
                  <li>
                    <a href={subOption2Link} rel="noreferrer" target="_blank">
                    <span class="list-icon">
                      <Icon data={requestForDemo} class="list-icon" />
                    </span>
                    <span class="list-label">{subOption2}</span>
                    </a>
                  </li>

                  <li>
                    <a href={subOption3Link} rel="noreferrer" target="_blank">
                    <span class="list-icon">
                      <Icon data={writeToUs} />
                    </span>
                    <span class="list-label">{subOption3}</span>
                    </a>
                  </li>
                  <li>
                    <a href={subOption4Link} rel="noreferrer" target="_blank">
                    <span class="list-icon">
                      <Icon data={whatsApp} />
                    </span>
                    <span class="list-label">{subOption4}</span>
                    </a>
                  </li>
                </ul>
              </div>
            </li>
          </ul>
        </div>
        <div class="header">
          <h1>{title}</h1>
        </div>
      </div>

      <div class="right-side">
        <div>
          <div>
            <div class="info">
              <div>{accountName}</div>
              &nbsp;|&nbsp;
              <div class="user-name">
                {userName}
                <div class="user-menu">
                  <div class="list-item">
                    <a href={myProfileLink} rel="noreferrer" target="_blank">
                    <span class="list-icon">

                      <Icon data={myProfile} />
                    </span>
                    <span class="list-label">My Profile</span>
                    </a>
                  </div>
                  <hr />
                  <!-- svelte-ignore a11y-click-events-have-key-events -->
                  <div on:click={onLogout}>
                    <span class="list-icon">
                      <Icon data={logout} />
                    </span>
                    <span class="list-label">Logout</span>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div>
            {expiryMassage}
            <button class="buttonSubscription">{buttonText}</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<style>
  .info {
    display: flex;
  }
  .nav-bar {
    display: flex;
    height: max-content;
    background-color: var(--bg-color, #fdd332);
  }

  .image-style {
    height: 80px;
    width: 80px;
    padding: 10px;
    border-radius: 20px;
    object-fit: cover;
  }

  .containt-style {
    width: 100%;
    display: flex;
    justify-content: space-between;
  }
  span {
    vertical-align: middle;
  }

  .containt-style ul {
    list-style: none;
    display: flex;
    padding: 0;
  }
  .list-style li {
    margin-right: 10px;
  }

  .list-style li:hover {
    font-weight: bold;
    cursor: pointer;
  }
  .arrow {
    border: solid black;
    border-width: 0 2px 2px 0;
    display: inline-block;
    padding: 2px 3px;
    margin: 3px;
  }
  .down {
    transform: rotate(45deg);
    -webkit-transform: rotate(45deg);
  }
  .sub-list-style {
    display: none;
    padding: 10px 0px;
    font-weight: normal;
  }
  .list-icon {
    margin-right: 10px;
  }

  .sub-list-style ul li {
    padding: 5px 15px;
    align-items: center;
    height: max-content;
    vertical-align: top;
    margin: 5px 0px;
  }

  .sub-list-style ul li a{
    text-decoration: none;
  }
  a:link, a:visited {
  color: black;
  text-align: center;
  text-decoration: none;
  display: inline-block;
}

a:hover, a:active {
  cursor: pointer;
}

  .list-style ul li:hover .sub-list-style {
    display: block;
    position: absolute;
    background-color: white;
    list-style: none;
    justify-items: center;
    border-radius: 5px;
    box-shadow: 0 5px 10px 0 rgba(0, 0, 0, 0.4);
  }

  .list-style ul li:hover .sub-list-style ul {
    display: block;
  }

  .sub-list-style ul li:hover {
    width: 100%;
    background-color: rgba(0, 100, 255, 0.2);
    font-weight: normal;
    justify-content: center;
    align-items: center;
  }

  .header {
    font-weight: lighter;
    font-size: smaller;
  }
  .header h1 {
    margin: 0;
    padding: 0;
  }

  .right-side {
    align-items: center;
    display: grid;
    text-align: end;
    margin-right: 10px;
  }
  .buttonSubscription {
    background-color: transparent;
    border: none;
    color: #0011ff;
  }

  hr {
    margin: 0 20px;
    color: #000;
    background-color: black;
  }

  .user-menu {
    display: none;
    position: absolute;
    cursor: pointer;
  }

  .user-menu div {
    margin: 5px 0px;
    padding: 0;
  }
  .user-menu div:hover {
    margin: 5px 0px;
    background-color: rgba(0, 100, 255, 0.2);
  }

  .user-name:hover .user-menu {
    position: absolute;
    display: block;
    background-color: white;
    cursor: pointer;
    text-align: left;
    white-space: nowrap;
    border-radius: 5px;
    right: 10px;
    width: max-content;
    box-shadow: 0 5px 10px 0 rgba(0, 0, 0, 0.4);
    font-weight: normal;
  }

  .user-name:hover .user-menu div {
    padding: 5px 15px;
  }
</style>
