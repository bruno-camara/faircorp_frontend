<template>
  <form action="/action_page.php">
    <label for="name">Name:</label><br>
    <input type="text" id="name" name="name"><br>
    <label for="lname">Window Status:</label><br>
    <input type="text" id="status" name="status"><br><br>
    <label for="name">Room Name:</label><br>
    <input type="text" id="rname" name="rname"><br>
    <label for="lname">Room Id:</label><br>
    <input type="number" id="rid" name="rid"><br><br>
    <input type="submit" value="Submit">
  </form>
</template>

<script>
export default {
  name: 'WindowForm'
}
</script>