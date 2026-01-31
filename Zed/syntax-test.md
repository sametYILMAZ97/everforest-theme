# Syntax Highlighting Test for Everforest Theme

## JavaScript/TypeScript (MERN Stack)

```javascript
// Comments are muted and italic
import React, { useState, useEffect } from 'react';
import axios from 'axios';

/**
 * Doc comments are also italic
 * @param {string} userId - The user ID
 */
const UserProfile = ({ userId }) => {
  const [user, setUser] = useState(null);
  const [loading, setLoading] = useState(true);
  const API_URL = 'https://api.example.com';
  
  useEffect(() => {
    const fetchUser = async () => {
      try {
        const response = await axios.get(`${API_URL}/users/${userId}`);
        setUser(response.data);
      } catch (error) {
        console.error('Error fetching user:', error);
      } finally {
        setLoading(false);
      }
    };
    
    fetchUser();
  }, [userId]);
  
  if (loading) return <div>Loading...</div>;
  
  return (
    <div className="user-profile">
      <h1>{user.name}</h1>
      <p>Email: {user.email}</p>
      <button onClick={() => console.log(user)}>Log User</button>
    </div>
  );
};

export default UserProfile;
```

## Node.js/Express Backend

```javascript
const express = require('express');
const mongoose = require('mongoose');
const jwt = require('jsonwebtoken');

const app = express();
const PORT = process.env.PORT || 3000;

// Middleware
app.use(express.json());

// MongoDB Schema
const UserSchema = new mongoose.Schema({
  name: { type: String, required: true },
  email: { type: String, unique: true, required: true },
  password: String,
  createdAt: { type: Date, default: Date.now }
});

const User = mongoose.model('User', UserSchema);

// Routes
app.post('/api/users', async (req, res) => {
  try {
    const user = new User(req.body);
    await user.save();
    res.status(201).json(user);
  } catch (error) {
    res.status(400).json({ error: error.message });
  }
});

app.listen(PORT, () => {
  console.log(`Server running on port ${PORT}`);
});
```

## Swift

```swift
import SwiftUI
import Combine

// Protocol definition
protocol UserServiceProtocol {
    func fetchUser(id: String) async throws -> User
}

// Model with Codable
struct User: Codable, Identifiable {
    let id: String
    var name: String
    var email: String
    var age: Int?
    
    enum CodingKeys: String, CodingKey {
        case id
        case name
        case email
        case age
    }
}

// SwiftUI View
@MainActor
class UserViewModel: ObservableObject {
    @Published var user: User?
    @Published var isLoading = false
    @Published var errorMessage: String?
    
    private let service: UserServiceProtocol
    private var cancellables = Set<AnyCancellable>()
    
    init(service: UserServiceProtocol) {
        self.service = service
    }
    
    func loadUser(id: String) async {
        isLoading = true
        defer { isLoading = false }
        
        do {
            user = try await service.fetchUser(id: id)
        } catch {
            errorMessage = error.localizedDescription
            print("Error loading user: \(error)")
        }
    }
}

struct UserProfileView: View {
    @StateObject private var viewModel: UserViewModel
    let userId: String
    
    var body: some View {
        VStack(spacing: 20) {
            if viewModel.isLoading {
                ProgressView("Loading...")
            } else if let user = viewModel.user {
                Text(user.name)
                    .font(.title)
                    .foregroundColor(.primary)
                
                Text(user.email)
                    .font(.body)
                    .foregroundColor(.secondary)
                
                if let age = user.age {
                    Text("Age: \(age)")
                }
            }
        }
        .padding()
        .task {
            await viewModel.loadUser(id: userId)
        }
    }
}
```

## HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>User Dashboard</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <!-- Main container -->
    <div class="container" id="main-content">
        <header>
            <h1>Welcome to Dashboard</h1>
            <nav class="navbar">
                <ul>
                    <li><a href="#home">Home</a></li>
                    <li><a href="#profile">Profile</a></li>
                    <li><a href="#settings">Settings</a></li>
                </ul>
            </nav>
        </header>
        
        <main>
            <section class="user-info">
                <h2>User Information</h2>
                <form action="/submit" method="POST">
                    <input type="text" name="username" placeholder="Enter username" required>
                    <input type="email" name="email" placeholder="Enter email" required>
                    <button type="submit">Submit</button>
                </form>
            </section>
        </main>
        
        <footer>&copy; 2024 Your Company</footer>
    </div>
    
    <script src="app.js"></script>
</body>
</html>
```

## CSS

```css
/* Root variables */
:root {
    --primary-color: #8DA101;
    --secondary-color: #3A94C5;
    --background: #FDF6E3;
    --text-color: #5C6A72;
}

/* Universal selector */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px;
}

.navbar ul {
    display: flex;
    list-style: none;
    gap: 1rem;
}

.navbar a {
    color: var(--text-color);
    text-decoration: none;
    transition: color 0.3s ease;
}

.navbar a:hover {
    color: var(--primary-color);
}

/* Pseudo-classes and pseudo-elements */
button::before {
    content: "→ ";
}

input:focus {
    outline: 2px solid var(--primary-color);
}

@media (max-width: 768px) {
    .container {
        padding: 10px;
    }
}
```

## Java with Spring Boot

```java
package com.example.demo.controller;

import com.example.demo.model.User;
import com.example.demo.service.UserService;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;

import javax.validation.Valid;
import java.util.List;
import java.util.Optional;

/**
 * REST Controller for User management
 * @author Your Name
 */
@RestController
@RequestMapping("/api/users")
@CrossOrigin(origins = "*")
public class UserController {
    
    private final UserService userService;
    
    @Autowired
    public UserController(UserService userService) {
        this.userService = userService;
    }
    
    /**
     * Get all users
     * @return List of all users
     */
    @GetMapping
    public ResponseEntity<List<User>> getAllUsers() {
        List<User> users = userService.findAll();
        return ResponseEntity.ok(users);
    }
    
    /**
     * Get user by ID
     * @param id User ID
     * @return User object or 404
     */
    @GetMapping("/{id}")
    public ResponseEntity<User> getUserById(@PathVariable Long id) {
        Optional<User> user = userService.findById(id);
        return user.map(ResponseEntity::ok)
                   .orElse(ResponseEntity.notFound().build());
    }
    
    /**
     * Create new user
     * @param user User object to create
     * @return Created user
     */
    @PostMapping
    public ResponseEntity<User> createUser(@Valid @RequestBody User user) {
        User savedUser = userService.save(user);
        return ResponseEntity.created(null).body(savedUser);
    }
    
    /**
     * Update existing user
     */
    @PutMapping("/{id}")
    public ResponseEntity<User> updateUser(
            @PathVariable Long id,
            @Valid @RequestBody User userDetails) {
        try {
            User updatedUser = userService.update(id, userDetails);
            return ResponseEntity.ok(updatedUser);
        } catch (Exception e) {
            return ResponseEntity.notFound().build();
        }
    }
    
    /**
     * Delete user
     */
    @DeleteMapping("/{id}")
    public ResponseEntity<Void> deleteUser(@PathVariable Long id) {
        userService.deleteById(id);
        return ResponseEntity.noContent().build();
    }
}
```

## Java Entity Class

```java
package com.example.demo.model;

import lombok.Data;
import lombok.NoArgsConstructor;
import lombok.AllArgsConstructor;

import javax.persistence.*;
import javax.validation.constraints.*;
import java.time.LocalDateTime;

@Entity
@Table(name = "users")
@Data
@NoArgsConstructor
@AllArgsConstructor
public class User {
    
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    
    @NotBlank(message = "Name is required")
    @Size(min = 2, max = 100)
    private String name;
    
    @Email(message = "Email should be valid")
    @NotNull
    @Column(unique = true)
    private String email;
    
    @NotBlank
    @Size(min = 6)
    private String password;
    
    @Min(18)
    @Max(120)
    private Integer age;
    
    @Enumerated(EnumType.STRING)
    private UserRole role;
    
    @Column(name = "created_at", nullable = false, updatable = false)
    private LocalDateTime createdAt;
    
    @PrePersist
    protected void onCreate() {
        createdAt = LocalDateTime.now();
    }
    
    public enum UserRole {
        USER, ADMIN, MODERATOR
    }
}
```

---

## Color Legend (Everforest Dark)

- **Comments**: `#859289` (gray-green, italic)
- **Strings**: `#A7C080` (green)
- **Keywords**: `#E67E80` (red, italic) - `import`, `const`, `let`, `if`, `async`, `await`, etc.
- **Functions**: `#A7C080` (green, bold)
- **Types/Classes**: `#DBBC7F` (yellow, italic)
- **Numbers/Booleans**: `#D699B6` (pink/magenta)
- **Operators**: `#E69875` (orange)
- **Properties/Variables**: `#D3C6AA` (beige)
- **Punctuation**: `#859289` (gray-green)
- **Tags (HTML/JSX)**: `#E69875` (orange)
- **Attributes**: `#DBBC7F` (yellow)
- **Annotations (@)**: `#DBBC7F` (yellow)
- **Links**: `#7FBBB3` (cyan)
- **Constants**: `#83C092` (cyan)

## Color Legend (Everforest Light)

- **Comments**: `#939F91` (gray, italic)
- **Strings**: `#8DA101` (olive green)
- **Keywords**: `#F85552` (red, italic)
- **Functions**: `#8DA101` (olive green, bold)
- **Types/Classes**: `#DFA000` (orange/yellow, italic)
- **Numbers/Booleans**: `#DF69BA` (pink/magenta)
- **Operators**: `#F57D26` (orange)
- **Properties/Variables**: `#5C6A72` (dark gray-blue)
- **Punctuation**: `#939F91` (gray)
- **Tags (HTML/JSX)**: `#F57D26` (orange)
- **Attributes**: `#DFA000` (orange/yellow)
- **Annotations (@)**: `#DFA000` (orange/yellow)
- **Links**: `#3A94C5` (blue)
- **Constants**: `#35A77C` (cyan/green)