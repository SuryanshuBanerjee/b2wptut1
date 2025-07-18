# First Lab Tut React 🎪

## See it Live

Link at: [https://suryanshubanerjee.github.io/b2wptut1/](https://suryanshubanerjee.github.io/b2wptut1/)

*(Yes, I know the URL looks like I mashed my keyboard. Don't judge.)*

## What's This?

Just your average React app where I built some *totally groundbreaking* components:
- A profile card (revolutionary, I know)
- Buttons that count clicks (Nobel Prize incoming)
- A grocery list that's color-coded (because why not?)

## Getting Started

### Option 1: The "I Actually Want to Learn" Path

Fire up your VS Code terminal and follow along:

1. **Create a new Vite + React app** (because create-react-app is so 2022)
   ```bash
   npm create vite@latest myfirstapp -- --template react
   ```
   
2. **Navigate to your shiny new project**
   ```bash
   cd myfirstapp
   ```

3. **Install dependencies** (grab a coffee, this takes a minute)
   ```bash
   npm install
   ```

4. **Replace the default App.jsx** with my masterpiece (scroll down to find the full code)

5. **Start the dev server**
   ```bash
   npm run dev
   ```

6. **Open your browser** and witness at `http://localhost:5173`

### Option 2: The "I Just Want It Working" Path

Too lazy for all that setup? I feel you. Just:

1. Scroll down and copy the entire `App.jsx` code below
2. Paste it into your existing React project
3. Delete whatever boring code was there before
4. Profit 

*Note: Yes, I committed the built files to GitHub instead of the source. I live dangerously.*

## 📁 Project Structure

```
My GitHub Repo/
├── index.html          # The built stuff
├── index-Cu4J7Dw8.js   # Vite's hash naming (good luck debugging)
├── index-Dtn62Xmo.css  # More mysterious hashes
├── vite.svg            # The logo nobody asked for
└── README.md           # You are here

My Local Project (if you're following along)/
├── src/
│   ├── App.jsx         # The actual code (see below)
│   ├── main.jsx        # Don't touch this
│   └── index.css       # Delete the default styles here
├── package.json        # Scary config stuff
└── index.html          # The HTML nobody looks at
```

*Yes, I deployed the dist folder directly. No, I'm not sorry.*

## Features That Will Not Blow Your Mind

- **Responsive Design**: Works on your PC! (Mobile users, you're on your own)
- **Interactive Cards**: They move when you hover! (I spent way too long on this)
- **State Management**: Each button remembers its count (until you refresh, then amnesia kicks in)
- **Beautiful Gradients**: Because solid colors are boring
- **Zero Dependencies**: Just React and my questionable CSS choices

## Known Issues

- The buttons don't sync their counts (it's a feature, not a bug)
- Hedy Lamarr's photo loads from imgur (hopefully it stays there forever)
- The grocery list is hardcoded (sorry, no adding your own veggies)

## The Actual Code

Since my GitHub repo only has the built files (because who needs source control for source code, am I right?), here's the entire `App.jsx` for your copy-pasting pleasure:

```jsx
import { useState } from 'react';

export default function ShowcaseApp() {
  const user = {
    name: 'Hedy Lamarr',
    imageUrl: 'https://i.imgur.com/yXOvdOSs.jpg',
    bio: 'Inventor & Actress'
  };

  const products = [
    { title: 'Cabbage', isFruit: false, id: 1 },
    { title: 'Garlic', isFruit: false, id: 2 },
    { title: 'Apple', isFruit: true, id: 3 },
  ];

  function CounterButton() {
    const [count, setCount] = useState(0);
    
    return (
      <button 
        onClick={() => setCount(count + 1)}
        style={{
          width: '100%',
          backgroundColor: '#3b82f6',
          color: 'white',
          fontWeight: '600',
          padding: '12px 16px',
          borderRadius: '8px',
          border: 'none',
          cursor: 'pointer',
          marginBottom: '8px',
          transition: 'all 0.2s',
        }}
        onMouseEnter={(e) => e.target.style.backgroundColor = '#2563eb'}
        onMouseLeave={(e) => e.target.style.backgroundColor = '#3b82f6'}
      >
        Clicked {count} times
      </button>
    );
  }

  const styles = {
    container: {
      minHeight: '100vh',
      width: '100vw',
      background: 'linear-gradient(135deg, #dbeafe 0%, #e0e7ff 100%)',
      padding: '40px',
      fontFamily: 'system-ui, -apple-system, sans-serif',
      boxSizing: 'border-box',
    },
    header: {
      textAlign: 'center',
      marginBottom: '60px',
    },
    title: {
      fontSize: '56px',
      fontWeight: 'bold',
      color: '#1f2937',
      margin: '0 0 16px 0',
    },
    subtitle: {
      color: '#6b7280',
      fontSize: '20px',
      margin: 0,
    },
    grid: {
      display: 'grid',
      gridTemplateColumns: 'repeat(3, 1fr)',
      gap: '32px',
      maxWidth: '1400px',
      margin: '0 auto',
    },
    card: {
      backgroundColor: 'white',
      borderRadius: '16px',
      boxShadow: '0 10px 25px rgba(0,0,0,0.1)',
      padding: '32px',
      transition: 'transform 0.2s, box-shadow 0.2s',
      height: '100%',
      display: 'flex',
      flexDirection: 'column',
    },
    cardTitle: {
      fontSize: '24px',
      fontWeight: 'bold',
      color: '#1f2937',
      textAlign: 'center',
      marginBottom: '20px',
    },
    footer: {
      textAlign: 'center',
      color: '#6b7280',
      fontSize: '16px',
      marginTop: '60px',
    }
  };

  return (
    <div style={styles.container}>
      <div style={styles.header}>
        <h1 style={styles.title}>My React Playground</h1>
        <p style={styles.subtitle}>Just some fun components I built ✨</p>
      </div>

      <div style={styles.grid}>
        <div 
          style={styles.card}
          onMouseEnter={(e) => {
            e.currentTarget.style.transform = 'translateY(-4px)';
            e.currentTarget.style.boxShadow = '0 20px 40px rgba(0,0,0,0.15)';
          }}
          onMouseLeave={(e) => {
            e.currentTarget.style.transform = 'translateY(0)';
            e.currentTarget.style.boxShadow = '0 10px 25px rgba(0,0,0,0.1)';
          }}
        >
          <h2 style={styles.cardTitle}>Featured Person</h2>
          <div style={{ display: 'flex', flexDirection: 'column', alignItems: 'center', flex: 1 }}>
            <img
              style={{
                width: '120px',
                height: '120px',
                borderRadius: '50%',
                marginBottom: '20px',
                border: '4px solid #dbeafe',
                boxShadow: '0 4px 8px rgba(0,0,0,0.1)',
              }}
              src={user.imageUrl}
              alt={`Photo of ${user.name}`}
            />
            <h3 style={{ fontSize: '22px', fontWeight: '600', color: '#374151', margin: '0 0 8px 0' }}>
              {user.name}
            </h3>
            <p style={{ color: '#6b7280', fontSize: '16px', margin: 0 }}>
              {user.bio}
            </p>
          </div>
        </div>

        <div 
          style={styles.card}
          onMouseEnter={(e) => {
            e.currentTarget.style.transform = 'translateY(-4px)';
            e.currentTarget.style.boxShadow = '0 20px 40px rgba(0,0,0,0.15)';
          }}
          onMouseLeave={(e) => {
            e.currentTarget.style.transform = 'translateY(0)';
            e.currentTarget.style.boxShadow = '0 10px 25px rgba(0,0,0,0.1)';
          }}
        >
          <h2 style={styles.cardTitle}>Button Playground</h2>
          <p style={{ color: '#6b7280', textAlign: 'center', marginBottom: '32px', fontSize: '16px' }}>
            Each button keeps its own count
          </p>
          <div style={{ flex: 1, display: 'flex', flexDirection: 'column', justifyContent: 'center' }}>
            <CounterButton />
            <CounterButton />
          </div>
        </div>

        <div 
          style={styles.card}
          onMouseEnter={(e) => {
            e.currentTarget.style.transform = 'translateY(-4px)';
            e.currentTarget.style.boxShadow = '0 20px 40px rgba(0,0,0,0.15)';
          }}
          onMouseLeave={(e) => {
            e.currentTarget.style.transform = 'translateY(0)';
            e.currentTarget.style.boxShadow = '0 10px 25px rgba(0,0,0,0.1)';
          }}
        >
          <h2 style={styles.cardTitle}>Grocery List</h2>
          <p style={{ color: '#6b7280', textAlign: 'center', marginBottom: '24px', fontSize: '16px' }}>
            Color-coded by type
          </p>
          <ul style={{ listStyle: 'none', padding: 0, margin: 0, flex: 1 }}>
            {products.map(product => (
              <li
                key={product.id}
                style={{
                  padding: '16px 20px',
                  borderRadius: '8px',
                  marginBottom: '12px',
                  borderLeft: '4px solid',
                  backgroundColor: product.isFruit ? '#fdf2f8' : '#f0fdf4',
                  color: product.isFruit ? '#be185d' : '#065f46',
                  borderLeftColor: product.isFruit ? '#ec4899' : '#10b981',
                }}
              >
                <span style={{ fontWeight: '500', fontSize: '16px' }}>{product.title}</span>
                <span style={{ fontSize: '14px', marginLeft: '8px', opacity: 0.7 }}>
                  ({product.isFruit ? 'Fruit' : 'Vegetable'})
                </span>
              </li>
            ))}
          </ul>
        </div>
      </div>

      <div style={styles.footer}>
        <p>Made with React & vanilla CSS 💙</p>
      </div>
    </div>
  );
}
```

## Why Though?

Look, we all start somewhere. 
