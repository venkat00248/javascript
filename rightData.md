import React, { useEffect, useState } from 'react';
import axios from 'axios';

const MyComponent = () => {
  const [userData, setUserData] = useState({});
  const [userPosts, setUserPosts] = useState([]);
  const [postComments, setPostComments] = useState([]);

  useEffect(() => {
    const fetchData = async () => {
      try {
        const [userResponse, postsResponse, commentsResponse] = await Promise.all([
          axios.get('https://jsonplaceholder.typicode.com/users'),
          axios.get('https://jsonplaceholder.typicode.com/posts?userId=1'),
          axios.get('https://jsonplaceholder.typicode.com/posts/1/comments')
        ]);

        setUserData(userResponse.data);
        setUserPosts(postsResponse.data);
        setPostComments(commentsResponse.data);
      } catch (error) {
        console.error('Error fetching data:', error);
      }
    };

    fetchData();
  }, []); // Empty dependency array to run the effect only once when the component mounts

  return (
    <div>
      <h2>User Data</h2>
      <pre>{JSON.stringify(userData, null, 2)}</pre>

      <h2>User Posts</h2>
      <pre>{JSON.stringify(userPosts, null, 2)}</pre>

      <h2>Post Comments</h2>
      <pre>{JSON.stringify(postComments, null, 2)}</pre>
    </div>
  );
};

export default MyComponent;
