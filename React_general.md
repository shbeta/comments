### how to use axios

### first method to use axios
````````````
useEffect( () => {
    async function fetchData() {
      let token = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyIjp7ImlkIjoiNWQ5MGFlMzY1ZTMzYTU1NTVjYWYwYjZlIn0sImlhdCI6MTU2OTc2NzU1NSwiZXhwIjoxNTcwMTI3NTU1fQ.sTaoAMFu7_XRWtyV9URAprGd_Mm6RWXzP8xBwy6pbSA';
      var result = await axios({
        method: "GET",
        url: 'http://localhost:5000/api/auth',
        headers: {
          "x-auth-token": token
        },
        // data: {"email": "ccc@gmail.com", "password": "1234567" }
      })

      setData(result);
      console.log(result)
    }
    fetchData();
  },[])
  
  `````````````````````

### second method to use axios

````````````````
  // method 2
  useEffect( () => {
    async function fetchData() {
      // let token = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyIjp7ImlkIjoiNWQ5MGFjMzlhMWUwMjMwNmFjOTcxNmRjIn0sImlhdCI6MTU3MDEyNzkxNCwiZXhwIjoxNTcwNDg3OTE0fQ.qhBdPAzezlYEcmwYdbD6yY-BalciNlZQHjdvSbfAJBg';
      
      var result = await axios.post('/api/auth',
        {"email": "bbb@gmail.com", "password": "1234567" },
        { "Content-Type": "application/json"}
      )

      setData(result);
      console.log(result)
    }
    fetchData();
  },[])
  
````````````````
### method 3

`````````````````
useEffect( () => {
    async function fetchData() {
      // let token = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyIjp7ImlkIjoiNWQ5MGFjMzlhMWUwMjMwNmFjOTcxNmRjIn0sImlhdCI6MTU3MDEyNzkxNCwiZXhwIjoxNTcwNDg3OTE0fQ.qhBdPAzezlYEcmwYdbD6yY-BalciNlZQHjdvSbfAJBg';
      var result = await axios.post('/api/users',
        {"name": "ahmad",
        "email": "vvvvv@gmail.com",
        "password": "1234567" },
        { "headers":{"Content-Type": "application/json"}}
      )

      setData(result);
      console.log(result)
    }
    fetchData();
  },[])
``````````
