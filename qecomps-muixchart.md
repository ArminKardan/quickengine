
#### MUI X Charts Support

The `MUI X Charts` library is pre-installed and fully supported in the QE Platform. Developers can seamlessly integrate powerful chart visualizations into their `Admin Panel` and `XWebsite` projects.

**Example:** The following demonstrates how to implement `PieChart`, `LineChart`, and `RadarChart` using `MUI X Charts`:

```jsx
import { LineChart, PieChart } from '@mui/x-charts';
import { Unstable_RadarChart as RadarChart } from '@mui/x-charts/RadarChart';

// Front-end function example
export default p => Component(p, Page);
const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => <div style={{ direction: z.lang.dir, padding: 10 }}>
  <w-cc style={{ direction: "ltr" }}>
    <f-x>
      <PieChart
        series={[
          {
            data: [
              { id: 0, value: 10, label: 'series A' },
              { id: 1, value: 15, label: 'series B' },
              { id: 2, value: 20, label: 'series C' },
            ],
          },
        ]}
        width={150}
        height={150} />
    </f-x>
    <f-x>
      <LineChart
        xAxis={[{ data: [1, 2, 3, 5, 8, 10] }]}
        series={[
          {
            data: [2, 5.5, 2, 8.5, 1.5, 5],
            area: true,
          },
        ]}
        width={300}
        height={200} />
    </f-x>
    <f-x>
      <RadarChart
        height={250}
        series={[{ label: 'Habib', data: [120, 98, 86, 99, 85, 65] }]}
        radar={{
          max: 120,
          metrics: ['Math', 'Chinese', 'English', 'Geography', 'Physics', 'History'],
        }} />
    </f-x>
  </w-cc>
</div>
```

**Layout Note:**

- The `<w-cc>` container provides horizontal alignment with `flex-wrap: wrap`, ensuring responsive layout across devices.
- The `direction: ltr` style is explicitly applied to ensure correct rendering, especially for users using RTL languages such as Persian or Arabic, since `MUI X Charts` does not support RTL rendering well.
- The `<f-x>` tag acts as a container similar to a `<div>`, used in QE to maintain consistent styling and structure.
