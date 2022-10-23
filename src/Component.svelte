<script>
  import { getContext } from "svelte";

  import imageLogo from "./new-mbc-logo.svg"
  export let bgColor, title;
  export let option1, option2, option3;
  export let subOption1, subOption2, subOption3, subOption4;
  export let subOption1Icon, subOption2Icon, subOption3Icon, subOption4Icon;
  export let accountName, expiryMassage, userName;
  export let buttonText;
  export let onLogout;
  // export let iconUrl;  

  const { styleable } = getContext("sdk");
  const component = getContext("component");
</script>

<div use:styleable={$component.styles}>
  <div class="nav-bar" style="--bg-color: {bgColor}">
    <img
      src="https://source.unsplash.com/random/200x200/"
      alt="Icon"
      class="image-style"
      
    />

    <div class="containt-style">
      <div>
        <div class="list-style">
          <ul>
            <li>{option1}</li>
            <li>{option2}</li>
            <li>
              {option3} <i class="arrow down" />
              <div class="sub-list-style">
                <ul>
                  <li>{subOption1}</li>
                  <li>{subOption2}</li>
                  <li>{subOption3}</li>
                  <li>{subOption4}</li>
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
              <div>{accountName} </div>
              &nbsp;|&nbsp;
              <div class="user-name">
                {userName}
                <div class="user-menu">
                  <div class="list-item">My Profile</div>
                  <button class="list-item div-btn" on:click={onLogout}>Logout</button>
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
    height: 80PX;
    width: 80PX;
    padding: 10px;
    border-radius: 20px;
    object-fit: cover;
  }

  .containt-style {
    width: 100%;
    display: flex;
    justify-content: space-between;
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

  .sub-list-style {
    display: none;
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
    margin-right: 20px;
  }
  .buttonSubscription {
    background-color: transparent;
    border: none;
    color: #0011ff;
  }
  .div-btn{
    width: 100%;
    background-color: transparent;
    border: none;
  }
  .div-btn:hover{
    width: 100%;
    background-color: transparent;
    border: none;
    font-weight: bold;
  }

  .list-style ul li:hover .sub-list-style {
    display: block;
    position: absolute;
    background-color: white;
    list-style: none;
    padding: 0;
    border-radius: 5px;
    box-shadow: 0 5px 10px 0 rgba(0, 0, 0, 0.4);
  }

  .list-style ul li:hover .sub-list-style ul {
    display: block;
    list-style: none;
    padding: 10px;
    font-weight: normal;
  }
  .list-style ul li:hover .sub-list-style ul li {
    padding: 5px;
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

  .user-menu {
    display: none;
    position: absolute;
  }
  
  .user-name:hover .user-menu {
    position: fixed;
    display: block;
    background-color: white;
    cursor: pointer;
    text-align: left;
    border-radius: 5px;
    box-shadow: 0 5px 10px 0 rgba(0, 0, 0, 0.4);
    font-weight: normal;
  }

  .user-menu div:hover{
    font-weight: bold;
  }
  .user-name:hover .user-menu div{
    padding: 5px 12px;
  }
</style>
