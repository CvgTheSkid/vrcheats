<!-- ...same head and body as before -->

<script>
  const firebaseConfig = {
    apiKey: "AIzaSyBtGwQeKlQCQpTv8Lzav7djmka6YQMIORI",
    authDomain: "cvsite-fe8b5.firebaseapp.com",
    projectId: "cvsite-fe8b5",
  };

  firebase.initializeApp(firebaseConfig);
  const auth = firebase.auth();
  const db = firebase.firestore();

  let currentUserRole = "viewer"; // default role

  // Auth functions
  function signUp() {
    const nickname = prompt("Enter your nickname:"); // Get nickname from user

    auth.createUserWithEmailAndPassword(email.value, password.value)
      .then(() => {
        alert("Signed up!");
        // Add user to roles with default "viewer" and store their nickname
        db.collection("roles").doc(email.value).set({ 
          role: "viewer", 
          nickname: nickname || "Guest" // Store nickname or default to "Guest"
        });
      });
  }

  function signIn() {
    auth.signInWithEmailAndPassword(email.value, password.value)
      .then(() => alert("Logged in!"));
  }

  function signOut() {
    auth.signOut().then(() => alert("Logged out"));
  }

  // Auth state
  auth.onAuthStateChanged(async user => {
    if (user) {
      // Fetch role and nickname from Firestore
      const doc = await db.collection("roles").doc(user.email).get();
      currentUserRole = doc.exists ? doc.data().role : "viewer";
      const nickname = doc.exists ? doc.data().nickname : "Guest";

      // Show upload form only if allowed
      upload.style.display = (currentUserRole === "admin" || currentUserRole === "uploader") ? "block" : "none";

      // Set global nickname
      window.currentNickname = nickname;
    } else {
      upload.style.display = "none";
    }
  });

  // Submit mod
  function submitMod() {
    const mod = {
      name: modName.value,
      link: modLink.value,
      desc: modDesc.value,
      uploader: window.currentNickname, // Use nickname
      time: new Date().toISOString()
    };
    db.collection("mods").add(mod).then(() => {
      alert("Mod submitted!");
      modName.value = modLink.value = modDesc.value = "";
    });
  }

  // Load mods
  db.collection("mods").orderBy("time", "desc").onSnapshot(snapshot => {
    modsList.innerHTML = "";
    snapshot.forEach(doc => {
      const mod = doc.data();
      modsList.innerHTML += `
        <div class="mod">
          <strong>${mod.name}</strong><br>
          <small>By: ${mod.uploader}</small><br>
          <p>${mod.desc || ""}</p>
          <a href="${mod.link}" target="_blank">Download</a>
        </div>
      `;
    });
  });
</script>
