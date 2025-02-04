# AWT
- Profile Picture:
- [Ref Link](https://medium.com/better-programming/create-a-letter-picture-like-google-with-react-ae12a7a4390e)
```
import React from 'react';
import './ProfilePicture.css'; // Import your CSS styles

const ProfilePicture = ({ name }) => {
  const initials = name.split(' ').map(part => part[0]).join('').toUpperCase(); // Extract initials

  return (
    <div className="profile-picture">
      {initials}
    </div>
  );
};

export default ProfilePicture; 
```
CSS Styling:
The crucial part is to style the .profile-picture class in your CSS file to achieve the desired look:
- Set a circular shape using ```border-radius: 50%.```
- Adjust background color, text color, font size, and padding to match Google's style.
Center the text within the circle using ```display: flex, align-items: center, and justify-content: center.```

Third-party libraries:
If you need more advanced features, consider using a dedicated React component library like @mui/material which provides a pre-built Avatar component with similar functionality.
