import React, { useState, useEffect } from 'react';

import './App.css'

function App() {
  const [quotes, setQuotes] = React.useState("");
  const [randomQuote, setRandomQuote] = React.useState("");

  React.useEffect(() => {
    async function fetchData() {
      const response = await fetch("https://type.fit/api/quotes")
      const data = await response.json();

      setQuotes(data);
      let randIndex = Math.floor(Math.random() * data.length);
      setRandomQuote(data[randIndex]);
    }
    fetchData();
  }, []);
const getNewQuote = () => {
  let randIndex = Math.floor(Math.random() * quotes.length);
  setRandomQuote(quotes[randIndex]);
}


  return (
    <>
      <div  id="quote-box">
      <p id="text">&quot;{randomQuote.text}&quot;</p>
  <h5 id="author">-{randomQuote.author}</h5>
  
  <a className="btn btn-warning"
                id="tweet-quote"
                href={'https://twitter.com/intent/tweet?hashtags=quotes&related=freecodecamp&text=' + 
                encodeURIComponent('"' + randomQuote.text + '"' + '---' + randomQuote.author)
                }
                target="_blank"
                
            >
            tweat
            </a>
            <a className="btn btn-danger"
                id="tumbler-quote"
                href={'https://www.tumblr.com/widgets/share/tool?posttype=quote&tags=quotes,freecodecamp&caption=' + 
                encodeURIComponent('"' + randomQuote.text + '"' + '---' +  randomQuote.author)
                }
                target="_blank"
                
            >
            tumblr
            </a>
            
  <button id="new-quote" className="btn btn-primary" onClick={getNewQuote}>New Quote</button> 
  </div>
    </>

  )
}

export default App

const colors = [
    "#16a085",
    "#27ae60",
    "#2c3e50",
    "#f39c12",
    "#e74c3c",
    "#fb6964",
    "#9b59b6",
    "#342224",
    "#73AB57",
    "#2c3e90",

  ]let randIndex = Math.floor(Math.random() * quotes.length);
  setRandomQuote(quotes[randIndex]);
  setColor(colors[randColorIndex])
#   D i g a f e - r a n d o m - q u o t e s  
 