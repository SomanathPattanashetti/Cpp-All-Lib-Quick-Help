<div align="center">
  
  <!-- Floating 3D C++ Logo -->
  <img src="https://user-images.githubusercontent.com/74038190/235294012-0a55e343-37ad-4b0f-924f-c84eb84e5d83.gif" width="100" />
  
  <br>

  <!-- Animated Modern Title -->
  <a href="https://git.io/typing-svg">
    <img src="https://readme-typing-svg.herokuapp.com?font=Orbitron&weight=900&size=40&pause=1000&color=00C8FF&background=00000000&center=true&vCenter=true&width=600&lines=C%2B%2B+ALL+LIB+QUICK+HELP;Competitive+Programming+Arsenal;Master+All+Libraries;Copy+%2B+Paste+Ready" alt="Typing SVG" />
  </a>

  <!-- Floating Tech Stack Icons -->
  <p align="center">
    <a href="https://skillicons.dev">
      <img src="https://skillicons.dev/icons?i=cpp,vscode,git,github,vim&theme=dark" />
    </a>
  </p>

  <!-- Glitch/Neon Badges -->
  <p>
    <img src="https://img.shields.io/badge/Language-C++17-blue?style=for-the-badge&logo=c%2B%2B&logoColor=white" />
    <img src="https://img.shields.io/badge/Focus-All_Libraries-orange?style=for-the-badge&logo=leetcode&logoColor=white" />
    <img src="https://img.shields.io/badge/Status-Maintained-success?style=for-the-badge&logo=activity&logoColor=white" />
  </p>

  <!-- Mission Code Line (Terminal Style) -->
  <br>
  <img src="https://img.shields.io/badge/const%20std::string%20MISSION%20%3D%20%22Mastering%20C%2B%2B%20Libraries%20for%20Interviews%22%3B-1e1e1e?style=flat-square&logo=windows-terminal&logoColor=white&labelColor=1e1e1e&color=1e1e1e" alt="Mission Code" height="40"/>
  <br>
  <br>
  
  <i>"Essential C++ library operations learned from solving Leetcode problems."</i>
  
  <br><br>

  <!-- Animated Divider -->
  <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif">
  
</div>

<br>

# 📖 Table of Contents - Interactive Library Guide

Click on any section to expand/collapse the content!

---

## 📚 `<string>` Library

<details>
<summary><b>🔹 String append() - 11 Overloaded Variants</b></summary>

### Quick Reference Table
| Overload | Meaning | Example | Result |
|----------|---------|---------|--------|
| `append(str)` | Whole string | `s.append(t)` | Full `t` |
| `append(str, pos)` | Substring from pos → end | `s.append(t, 3)` | `"DEFG"` |
| `append(str, pos, count)` | Substring pos → pos+count | `s.append(t, 1, 2)` | `"BC"` |
| `append(cstr)` | Full C-string | `s.append("Hi")` | `"Hi"` |
| `append(cstr, count)` | First count chars | `s.append(arr, 3)` | `"ABC"` |
| `append(count, ch)` | Repeated char | `s.append(4, '*')` | `"****"` |
| `append(it1, it2)` | Range add | `append(t.begin(), t.end())` | Full `t` |
| `append(ptr1, ptr2)` | Char pointer range | `append(arr+2, arr+5)` | `"CDE"` |
| `append({'a','b'})` | Initializer list | `append({'X','Y'})` | `"XY"` |
| `append(string_view)` | Full string_view | `append(sv)` | `"Alice"` |
| `append(sv, pos, count)` | string_view substring | `append(sv, 4, 3)` | `"app"` |

<details>
<summary><b>Method 1️⃣: append(const string& str)</b></summary>

**Purpose:** Appends the entire string

```cpp
string s = "Hello ";
string t = "World";
s.append(t);
cout << s;  // Output: Hello World
```

**Use Case:** Concatenating complete strings

</details>

<details>
<summary><b>Method 2️⃣: append(const string& str, size_t pos)</b></summary>

**Purpose:** Appends substring from position `pos` to end

```cpp
string s = "Data ";
string t = "ABCDEFG";
s.append(t, 3);     // Start at index 3 → 'D'
cout << s;          // Output: Data DEFG
```

**Index Mapping:** `A(0) B(1) C(2) D(3) E(4) F(5) G(6)`

**Use Case:** Extracting suffix of a string

</details>

<details>
<summary><b>Method 3️⃣: append(const string& str, size_t pos, size_t count)</b></summary>

**Purpose:** Appends substring from `pos` for `count` characters

```cpp
string s = "Data ";
string t = "ABCDEFG";
s.append(t, 1, 2);  // Start at index 1, take 2 chars → 'BC'
cout << s;          // Output: Data BC
```

**Use Case:** Extracting specific substring range

</details>

<details>
<summary><b>Method 4️⃣: append(const char* cstr)</b></summary>

**Purpose:** Appends a null-terminated C-string

```cpp
string s = "ID: ";
s.append("Alpha");
cout << s;          // Output: ID: Alpha
```

**Use Case:** Adding literal strings or C-style strings

</details>

<details>
<summary><b>Method 5️⃣: append(const char* cstr, size_t count)</b></summary>

**Purpose:** Appends first `count` characters from C-string

```cpp
string s = "Code: ";
char arr[] = "ABCDEFG";
s.append(arr, 3);   // Take first 3 chars
cout << s;          // Output: Code: ABC
```

**Use Case:** Partial C-string concatenation

</details>

<details>
<summary><b>Method 6️⃣: append(size_t count, char ch)</b></summary>

**Purpose:** Appends character `ch` repeated `count` times

```cpp
string s = "Load";
s.append(4, '.');
cout << s;          // Output: Load....
```

**Use Case:** Creating separators, padding, or repeated patterns

```cpp
// Creating a separator line
string line = "";
line.append(40, '-');
cout << line;       // Output: ----------------------------------------
```

</details>

<details>
<summary><b>Method 7️⃣: append(InputIterator first, InputIterator last)</b></summary>

**Purpose:** Appends range of characters from iterators

```cpp
string s = "Hello ";
string t = "World!!!";
s.append(t.begin(), t.begin() + 5);  // Take first 5 chars
cout << s;          // Output: Hello World
```

**Advanced Example:**
```cpp
vector<char> chars = {'A', 'B', 'C', 'D'};
string result = "Chars: ";
result.append(chars.begin(), chars.end());
cout << result;     // Output: Chars: ABCD
```

**Use Case:** Building strings from iterators, vectors, or containers

</details>

<details>
<summary><b>Method 8️⃣: append(const char* first, const char* last)</b></summary>

**Purpose:** Appends characters from memory range `[first, last)`

```cpp
string s = "Start ";
const char* arr = "ABCDEFG";
s.append(arr + 2, arr + 5);   // From 'C' to 'E' (index 2 → 4)
cout << s;          // Output: Start CDE
```

**Index Mapping:** 
- `arr + 2` → `'C'` (index 2)
- `arr + 5` → stop before index 5 (`'F'`)
- Appended chars = `"CDE"`

**Use Case:** Working with C-style string pointers and ranges

</details>

<details>
<summary><b>Method 9️⃣: append(initializer_list&lt;char&gt;)</b></summary>

**Purpose:** Adds characters written inside `{}`

```cpp
string s = "Hello";
s.append({' ', 'X', 'Y', 'Z'});
cout << s;          // Output: Hello XYZ
```

**Modern Example:**
```cpp
string password = "Pass";
password.append({'@', '1', '2', '3'});
cout << password;   // Output: Pass@123
```

**Use Case:** Inline character lists (C++11+), rarely used but elegant

</details>

<details>
<summary><b>Method 🔟: append(string_view sv)</b></summary>

**Purpose:** Appends everything from `string_view`

```cpp
string s = "Name: ";
string_view sv = "Alice";
s.append(sv);
cout << s;          // Output: Name: Alice
```

**Advantage:** No copying of the view until append - efficient!

**Use Case:** Modern C++17+ code with string_view parameters

</details>

<details>
<summary><b>Method 1️⃣1️⃣: append(string_view sv, size_t pos, size_t count = npos)</b></summary>

**Purpose:** Appends a substring of `string_view`

```cpp
string s = "Fruit: ";
string_view sv = "Pineapple";

// pos = 4  → start at 'a'
// count = 3 → take 3 chars
s.append(sv, 4, 3);   // "app"
cout << s;            // Output: Fruit: app
```

**Index Mapping:** `P(0) i(1) n(2) e(3) a(4) p(5) p(6) l(7) e(8)`
- Start at index 4 → `'a'`
- Take 3 chars → `"app"`

**Use Case:** Efficient substring extraction from string_view without copies

</details>

### 🎯 All Modern Methods at a Glance

| Syntax | Example | Output |
|--------|---------|--------|
| `append(ptr1, ptr2)` | `append(arr+2, arr+5)` | `"CDE"` |
| `append({'a','b'})` | `append({'X','Y'})` | `"XY"` |
| `append(string_view)` | `append(sv)` | `"Alice"` |
| `append(sv, pos, count)` | `append(sv, 4, 3)` | `"app"` |

### 🎯 Common Patterns & Tips

**Pattern 1: Building Dynamic Strings**
```cpp
string result = "";
result.append("User: ");
result.append(username);
result.append(" (ID: ");
result.append(to_string(id));
result.append(")");
// Output: User: John (ID: 12345)
```

**Pattern 2: Creating Formatted Output**
```cpp
string header = "";
header.append(20, '=');
header.append(" REPORT ");
header.append(20, '=');
// Output: ==================== REPORT ====================
```

**Pattern 3: Efficient Substring Extraction**
```cpp
string data = "2024-12-02";
string year = "";
year.append(data, 0, 4);    // Extract year: "2024"
string month = "";
month.append(data, 5, 2);   // Extract month: "12"
```

**Benefit:** Fast string concatenation without creating temporary objects, especially useful in loops

### 💡 Performance Notes

- **append() vs operator+:** `append()` is generally faster for multiple concatenations
- **Reserve space:** Use `s.reserve(size)` before multiple appends to avoid reallocations
- **Return value:** All `append()` overloads return reference to `*this`, allowing chaining

**Chaining Example:**
```cpp
string s = "C++";
s.append(" is").append(" ").append("awesome!");
cout << s;  // Output: C++ is awesome!
```

</details>

<details>
<summary><b>🔹 String substr() - Extract Substrings</b></summary>

### Coming Soon! 🚧
Add your `substr()` documentation here with all variants and examples.

</details>

<details>
<summary><b>🔹 String find() - Search Operations</b></summary>

### Coming Soon! 🚧
Add your `find()` documentation here with all variants and examples.

</details>

---

## 🗂️ `<algorithm>` Library

<details>
<summary><b>🔹 sort() - Sorting Operations</b></summary>

### Coming Soon! 🚧
Add your `sort()` documentation here with custom comparators.

</details>

<details>
<summary><b>🔹 binary_search() - Search in Sorted Range</b></summary>

### Coming Soon! 🚧
Add your `binary_search()` documentation here.

</details>

---

## 📦 `<vector>` Library

<details>
<summary><b>🔹 Vector Operations</b></summary>

### Coming Soon! 🚧
Add your vector operations documentation here.

</details>

---

## 🗺️ `<map>` & `<unordered_map>` Library

<details>
<summary><b>🔹 Map Operations</b></summary>

### Coming Soon! 🚧
Add your map operations documentation here.

</details>

---

## 🔢 `<queue>` & `<priority_queue>` Library

<details>
<summary><b>🔹 Priority Queue with Custom Comparators</b></summary>

### Coming Soon! 🚧
Add your priority queue documentation here (you can copy from your STL Quick Help repo!).

</details>

---

<div align="center">
  <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif">
</div>

## 📝 Important Note: C++ String Parameter Pattern 📌

<details>
<summary><b>Click to expand: Understanding pos/length Pattern</b></summary>

In C++ (especially with `std::string`, containers, and algorithms), the most common pattern for built-in library functions is:

### ✅ `pos, length` (or `pos, count`) is the MOST COMMON parameter pattern

This pattern appears in many string functions:

#### ✔ substr(pos, length)
```cpp
s.substr(2, 4);    // start at index 2, take 4 chars
```

#### ✔ append(str, pos, length)
```cpp
s.append(t, 3, 5); // from pos=3 take 5 chars
```

#### ✔ assign(str, pos, length)
```cpp
s.assign(t, 1, 3);
```

#### ✔ replace(pos, len, replacement)
```cpp
s.replace(2, 3, "Hi");
```

#### ✔ erase(pos, len)
```cpp
s.erase(1, 2);
```

#### ✔ insert(pos, str, pos2, len)
```cpp
s.insert(3, t, 1, 4);
```

---

### ⭐ General Rule for Strings in C++

Most string functions follow this pattern:
- **`pos`** = starting index
- **`len`** = how many characters to take

This is true for:
- `substr()`
- `append()`
- `assign()`
- `insert()`
- `replace()`
- `erase()`

**Why?** Because this pattern is intuitive and consistent across the standard library.

---

### ❗ Where the pattern changes

There are **two places** where this pattern does NOT apply:

#### ❌ C-string overloads (`char*`)
```cpp
append(char* s, size_t n);   // n = count, NOT pos!
```

#### ❌ Iterators
```cpp
append(it_begin, it_end);    // range [begin, end)
```

**Other than these two exceptions**, the C++ string library follows `pos/length` everywhere.

</details>

---

<div align="center">
  <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif">
  <br>
  <i>Happy Coding! 🚀</i>
  <br><br>
  <b>⭐ Star this repo if you find it helpful! ⭐</b>
</div>
