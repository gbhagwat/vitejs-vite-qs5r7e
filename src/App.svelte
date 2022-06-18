<script>
const roleHolders = [
  {userId: 'Madden.Bhagwat'},
  {userId: 'Gabrielle.Bhagwat'},
  {userId: 'Anjali.Bhagwat'},
  {userId: 'Sagar.Bhagwat'},
  {userId: 'Jack.Bhagwat'},
  {userId: 'Evelyn.Bhagwat'},
  {userId: 'Andrew.Zwilling'},
  {userId: 'Anastasiya.Zwilling'},
  {userId: 'Jacqueline.Zwilling'},
  {userId: 'William.Zwilling'},
  {userId: 'Sonia.Kelkar'},
  {userId: 'Saurabh.Kelkar'},
  {userId: 'Sarthak.Kelkar'}          
];

  let users = [];

roleHolders.forEach((usr) => {
  let firstName = usr.userId.split(".")[0];
  let lastName = usr.userId.split(".")[1];  

  users.push(usr);

  usr['firstName'] = firstName;
  usr['lastName'] = lastName;

  // users = users.sort((a, b) => a.firstName.localeCompare(b.firstName))
  // users = users.sort((a, b) => a.lastName.localeCompare(b.lastName))
  

  const map = new Map();
  users.sort((a, b) => a.firstName.localeCompare(b.firstName))
  .sort((a, b) => a.lastName.localeCompare(b.lastName))
  .map((usr) => { usr['displayName'] = usr.firstName + ' ' + usr.lastName });
  //users.forEach((usr) => { usr['displayName'] = usr.firstName + ' ' + usr.lastName });

});

//console.log(users)
const list = Array.from(users.values());
console.log(list)

  // display name can be shown in svelte ui {firstName} {lastName}

</script>

<ul>
{#each list as item}
  <li>
  {item.displayName}
  </li>
{/each}
</ul>
