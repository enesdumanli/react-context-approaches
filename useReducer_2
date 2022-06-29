import { createContext, useContext, useState, useReducer } from 'react';

const ThemeContext = createContext();

export default function MyApp() {

  const reducer = (state,action) => {
    switch(action.type){
        case 'CHANGE_THEME':
        	if(state.theme=='dark'){
              return{
              ...state,
              theme:'light'
            	}
            }
        	else{
              return{
                ...state,
                theme:'dark'
              	}
            }
    	}
  }

  
  const initial_state = {theme:'dark'}
  const [state,dispatch] = useReducer(reducer,initial_state)
  const value = {
    ...state, 
    changeTheme : () => { dispatch({type:'CHANGE_THEME'}) }
}
  
  
  return (
    <ThemeContext.Provider value={value}>
      <Form />
    </ThemeContext.Provider>
  )
}

function Form() {
  return (
    <Panel  title="Welcome">
      <Button >Change Theme</Button>
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
  const {theme,changeTheme} = useContext(ThemeContext);
  const className = 'button-' + theme;
  return (
    <button onClick={changeTheme} className={className}>
      {children}
    </button>
  );
}
