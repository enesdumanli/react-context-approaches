import { createContext, useContext, useState } from 'react';

const ThemeContext = createContext();

export default function MyApp() {

  const [theme,setTheme] = useState('dark')
  
  return (
    <ThemeContext.Provider value={{theme,setTheme}}>
      <Form />
    </ThemeContext.Provider>
  )
}

function Form() {
  return (
    <Panel title="Welcome">
      <Button>Change Theme</Button>
    </Panel>
  );
}

function Panel({ title, children }) {
  const {theme} = useContext(ThemeContext);
  const className = 'panel-' + theme;
  return (
    <section className={className}>
      <h1>{title}</h1>
      {children}
    </section>
  )
}

function Button({ children }) { 
  const {theme,setTheme} = useContext(ThemeContext);
  const className = 'button-' + theme;
  return (
    <button onClick={()=> theme=='dark' ? setTheme('light') : setTheme('dark')  } className={className}>
      {children}
    </button>
  );
}
