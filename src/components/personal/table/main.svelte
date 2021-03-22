<script>
  import Dictionary from "../../../helpers/Dictionary.helper"
</script>

<div class="content">
  <h2>{Dictionary.main.headers}</h2>
  <div class="text">{Dictionary.main.status}</div>
  <img src="./img/main-photo.png" alt="personal_photo" class="images" />
  <div class="text">{Dictionary.main.personalInfo}</div>
</div>

<style>
  .content {
    width: 100%;
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
  }
  .text {
    font-size: 20px;
    padding: 20px 0;
    text-align: center;
  }

  .images {
    width: 200px;
    height: 200px;
    border-radius: 50%;
  }
</style>
