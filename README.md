// exwallet-app/src/App.jsx import React from "react"; import { BrowserRouter as Router, Routes, Route } from "react-router-dom"; import Home from "./pages/Home"; import Login from "./pages/Login"; import Admin from "./pages/Admin"; import Dashboard from "./pages/Dashboard";

export default function App() { return ( <Router> <Routes> <Route path="/" element={<Home />} /> <Route path="/login" element={<Login />} /> <Route path="/admin" element={<Admin />} /> <Route path="/dashboard" element={<Dashboard />} /> </Routes> </Router> ); }

// exwallet-app/src/pages/Home.jsx import React from "react"; import { Link } from "react-router-dom";

export default function Home() { return ( <div className="min-h-screen flex flex-col items-center justify-center"> <h1 className="text-3xl font-bold mb-4">Welcome to ExWallet</h1> <Link to="/login" className="text-blue-500">Login</Link> </div> ); }

// exwallet-app/src/pages/Login.jsx import React, { useState } from "react"; import { useNavigate } from "react-router-dom";

export default function Login() { const [username, setUsername] = useState(""); const [password, setPassword] = useState(""); const navigate = useNavigate();

const handleLogin = (e) => { e.preventDefault(); if (username === "admin" && password === "admin") { navigate("/admin"); } else { navigate("/dashboard"); } };

return ( <form
onSubmit={handleLogin}
className="min-h-screen flex flex-col items-center justify-center"
> <h2 className="text-2xl font-bold mb-4">Login</h2> <input className="border p-2 mb-2" placeholder="Username" onChange={(e) => setUsername(e.target.value)} /> <input className="border p-2 mb-2" type="password" placeholder="Password" onChange={(e) => setPassword(e.target.value)} /> <button className="bg-blue-500 text-white px-4 py-2">Login</button> </form> ); }

// exwallet-app/src/pages/Admin.jsx import React from "react";

export default function Admin() { return ( <div className="min-h-screen p-8"> <h1 className="text-3xl font-bold mb-4">Admin Panel</h1> <p>Manage users, agents, and transactions here.</p> </div> ); }

// exwallet-app/src/pages/Dashboard.jsx import React from "react";

export default function Dashboard() { return ( <div className="min-h-screen p-8"> <h1 className="text-2xl font-bold">User Dashboard</h1> <p>Balance: ৳500000</p> </div> ); }

# E-wallet-
Game Education 
