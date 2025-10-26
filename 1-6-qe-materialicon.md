
## 🎨 Material Icons Support in QE

QE fully supports [Material Icons](https://mui.com/material-ui/material-icons/), allowing you to easily integrate high-quality icons into your front-end applications, including `microservice` and `xwebsite` projects.

Material Icons are pre-installed on QE using the following command:

```bash
yarn add @mui/icons-material @mui/material @emotion/styled @emotion/react
```

This means you can immediately start using icons in your React components.

### ✅ Example: Using Material Icons in Front-End

Below is a practical example demonstrating how to import and use several Material Icons inside a QE front-end function:

```jsx
import AddReactionIcon from '@mui/icons-material/AddReaction';
import AccountBalanceIcon from '@mui/icons-material/AccountBalance';
import BuildIcon from '@mui/icons-material/Build';
import BusinessCenterIcon from '@mui/icons-material/BusinessCenter';
import CameraAltIcon from '@mui/icons-material/CameraAlt';

// Front-end function
export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      <AddReactionIcon sx={{ fontSize: 40, color: "#2E951E" }} />
      <AccountBalanceIcon sx={{ fontSize: 35, color: "#1E4895" }} />
      <BuildIcon sx={{ fontSize: 30, color: "#951E85" }} />
      <BusinessCenterIcon sx={{ fontSize: 30, color: "#00AC98" }} />
      <CameraAltIcon sx={{ fontSize: 30, color: "#971D1D" }} />
    </div>
  );
};
```
