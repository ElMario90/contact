# contact
Make a firebase databse for my contact form on my webpage

  
  <script>
src="https://www.gstatic.com/firebasejs/9.6.7/firebase.js"; 
</script>  
  
      <script src="script.js"></script>


</body>   
</head> 
</html> 



//Javascript part


document.getElementById('contactForm').addEventListener('submit', submitForm);


const config = {
  apiKey: "AIzaSyC5sLviYrfP_kE1jnxQDHw6ZhKOEYnqS5U",
  authDomain: "website-4e704.firebaseapp.com",
  databaseURL: "https://website-4e704-default-rtdb.firebaseio.com",
  projectId: "website-4e704",
  storageBucket: "website-4e704.appspot.com",
  messagingSenderId: "46837114708",
  appId: "1:46837114708:web:389fb91480b807d9a3cac1",
  measurementId: "G-P6JQCJHHPF"
};

firebase.initializeApp(config);

// references messages collection
var messagesRef = firebase.database().ref('messages');





// It says that firebase is not defined, does anyone have a solution to this problem

//submit form
function submitForm(e){
  e.preventDefault();
  
  var email = getInputVal('email');
  var country = getInputVal('country');
  var subject = getInputVal('subject');

  console.log(email);
  saveMessage(email,country,subject)
}

// function to get form values
function getInputVal(id){
  return document.getElementById(id).value;
  
}


// save message to firebase

function saveMessage(email,country,subject){
  var newMessageRef = messagesRef.push;
  newMessageRef.set({
    email:email,
    country:country,
    subject:subject
    
  });
}
