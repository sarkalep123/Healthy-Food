# Healthy-Food

This is my repo

# Container.jsx

import styles from "./Container.module.css";

const Container = ({ children }) => {
return <div className={styles.container}>{children}</div>;
};
export default Container;

# Container.Module.css

import { StrictMode } from 'react'
import { createRoot } from 'react-dom/client'
import './index.css'
import App from './App.jsx'

createRoot(document.getElementById('root')).render(
<StrictMode>
<App />
</StrictMode>,
)

# ErrorMessage.jsx

import { StrictMode } from 'react'
import { createRoot } from 'react-dom/client'
import './index.css'
import App from './App.jsx'

createRoot(document.getElementById('root')).render(
<StrictMode>
<App />
</StrictMode>,
)

# FoodInput.jsx

import styles from "./FoodInput.module.css";

const FoodInput = ({ handleKeyDown }) => {
return (
<input
      type="text"
      placeholder="Enter Food Item here"
      className={styles.foodInput}
      onKeyDown={handleKeyDown}
    />
);
};
export default FoodInput;

# FoodInput.Module.css

import { StrictMode } from 'react'
import { createRoot } from 'react-dom/client'
import './index.css'
import App from './App.jsx'

createRoot(document.getElementById('root')).render(
<StrictMode>
<App />
</StrictMode>,
)

# FoodItem.jsx

import { useState } from "react";
import Item from "./Item";

const FoodItems = ({ items }) => {
let [activeItems, setActiveItems] = useState([]);

let onBuyButton = (item, event) => {
let newItems = [...activeItems, item];
setActiveItems(newItems);
};

return (
<ul className="list-group">
{items.map((item) => (
<Item
key={item}
foodItem={item}
bought={activeItems.includes(item)}
handleBuyButton={(event) => onBuyButton(item, event)} ></Item>
))}
</ul>
);
};
export default FoodItems;

# Item.jsx

import { StrictMode } from 'react'
import { createRoot } from 'react-dom/client'
import './index.css'
import App from './App.jsx'

createRoot(document.getElementById('root')).render(
<StrictMode>
<App />
</StrictMode>,
)

# Item.Module.css

import { StrictMode } from 'react'
import { createRoot } from 'react-dom/client'
import './index.css'
import App from './App.jsx'

createRoot(document.getElementById('root')).render(
<StrictMode>

# App.css

.food-heading {
color: brown;
text-align: center;
}

# App.jsx

import FoodItems from "./components/FoodItems";
import ErrorMessage from "./components/ErrorMessage";
import "bootstrap/dist/css/bootstrap.min.css";
import "./App.css";
import Container from "./components/Container";
import FoodInput from "./components/FoodInput";
import { useState } from "react";

function App() {
let [foodItems, setFoodItems] = useState([]);

const onKeyDown = (event) => {
if (event.key === "Enter") {
let newFoodItem = event.target.value;
event.target.value = " ";
let newItems = [...foodItems, newFoodItem];
setFoodItems(newItems);
}
};

return (
<>
<Container>
<h1 className="food-heading">Healthy Food</h1>
<FoodInput handleKeyDown={onKeyDown}></FoodInput>
<ErrorMessage items={foodItems}></ErrorMessage>
<FoodItems items={foodItems}></FoodItems>
</Container>
</>
);
}

export default App;

# Main.jsx

import { StrictMode } from 'react'
import { createRoot } from 'react-dom/client'
import './index.css'
import App from './App.jsx'

createRoot(document.getElementById('root')).render(
<StrictMode>
<App />
</StrictMode>,
)
