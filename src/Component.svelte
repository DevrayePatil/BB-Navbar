<script>
  import { getContext } from "svelte";
  import Icon from "svelte-icon";

  import MBCLogo from "./resources/new-mbc-logo.svg";

  import videoCamera from "./resources/video-camera.svg";
  import requestForDemo from "./resources/request-for-demo.svg";
  import writeToUs from "./resources/write-to-us.svg";
  import whatsApp from "./resources/whatsapp.svg";

  import projectMenuIcon from "./resources/kebab-icon.svg";

  import myProfile from "./resources/my-profile.svg";
  import logout from "./resources/logout.svg";

  import cloneIcon from "./resources/clone.svg";
  import exportIcon from "./resources/export.svg";
  import printIcon from "./resources/print.svg";
  import dropdownIcon from "./resources/dropdown-icon.svg";

  export let bgColor, title;
  export let option1, option2, option3;
  export let subOption1, subOption2, subOption3, subOption4;
  export let accountName, expiryMassage, userName;
  export let buttonText;
  export let onLogout;

  export let option1Link, option2Link;
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

    <div class="container-style">
      <div>
        <div class="list-style">
          <ul>
            <li><a href={option1Link} rel="noreferrer">{option1}</a></li>
            <li><a href={option2Link} rel="noreferrer">{option2}</a></li>
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
                        <Icon data={requestForDemo} />
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
          <span class="project-list-icon"
            ><Icon data={projectMenuIcon} />
            <div class="project-list">
              <ul>
                <li>
                  <span class="list-icon">
                    <Icon data={cloneIcon} />
                  </span>
                  Clone
                </li>
                <li class="expand-list">
                  <span class="list-icon">
                    <Icon data={exportIcon} />
                  </span>
                  Export
                  <i class="expand-list-icon right">
                    <Icon data={dropdownIcon} size="10px"/>
                  </i>
                  <div class="expanded-list">
                    <ul>
                      <li>Export in Exal</li>
                      <li>Export in PDF</li>
                    </ul>
                  </div>
                </li>
                <li class="expand-list">
                  <span class="list-icon">
                    <Icon data={printIcon} />
                  </span>
                  Print
                  <i class="expand-list-icon">
                    <Icon data={dropdownIcon} size="10px"/>
                  </i>
                  <div class="expanded-list">
                    <ul>
                      <li>Budgeted Cost</li>
                      <li>Budgeted & Estimated Cost</li>
                      <li>Estimated Cost (Summery)</li>
                      <li>Estimated Cost (Detailed)</li>
                    </ul>
                  </div>
                </li>
              </ul>
            </div>
          </span>
        </div>
      </div>

      <div class="right-side">
        <div>
          <div>
            <div class="user-information">
              <div>{accountName}</div>
              &nbsp;| &nbsp;
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
  * {
    margin: 0;
    padding: 0;
  }
  span {
    vertical-align: middle;
  }
  .user-information {
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

  .container-style {
    width: 100%;
    display: flex;
    justify-content: space-between;
    padding: 5px;
  }

  .list-style ul {
    list-style: none;
    display: flex;
    padding: 0;
  }

  .list-style ul li {
    margin-right: 10px;
    color: #000;
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
  .right {
    transform: rotate(270deg);
    -webkit-transform: rotate(270deg);
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

  .sub-list-style ul li a {
    text-decoration: none;
  }
  a:link,
  a:visited {
    color: black;
    text-align: center;
    text-decoration: none;
    display: inline-block;
  }

  a:hover,
  a:active {
    cursor: pointer;
  }

  .list-style ul li:hover .sub-list-style {
    z-index: 1;
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
    display: flex;
    margin-top: 5px;
    font-size: small;
  }

  .header span {
    margin-top: 8px;
  }

  .project-list {
    display: none;
  }

  .project-list ul li{
    width: 100%;
    border-color: tomato;

  }
  .project-list:hover {
    background-color: #678;
  }
  .project-list ul li:hover{
    background-color: rgba(0, 100, 255, 0.2);
  }
  .project-list-icon:hover .project-list {
    z-index: 1;
    display: block;
    position: absolute;
    background-color: white;
    border-radius: 5px;
    box-shadow: 0 5px 10px 0 rgba(0, 0, 0, 0.4);
  }

  .project-list-icon:hover .project-list ul {
    display: block;
  }
  .project-list-icon:hover .project-list ul li{
    padding: 5px 10px;
    margin: 5px 0;
    white-space: nowrap;
  }
  .expand-list-icon{
    float: right;
    margin-top: 5px;
    margin-left: 20px;
      transform: rotate(-90deg);
      -webkit-transform: rotate(-90deg);
  }
  .expanded-list{
    display: none;
  }
  .expand-list:hover .expanded-list{
    display: block;
    position: absolute;
    margin-left: 105px;
    margin-top: -25px;
    border-radius: 5px;

    background-color: white;
    box-shadow: 0 5px 10px 0 rgba(0, 0, 0, 0.4);

  }

   .expand-list:hover .expanded-list ul li{
   padding: 5px 20px;
    margin: 5px 0;
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
    z-index: 1;
    width: max-content;
    box-shadow: 0 5px 10px 0 rgba(0, 0, 0, 0.4);
    font-weight: normal;
  }

  .user-name:hover .user-menu div {
    padding: 5px 15px;
  }
</style>
