#  Objects & Packfiles : 

## 📁 .git/objects – The Heart of Git

Git stores everything in `.git/objects/` using four core object types:

| Object Type | Description |
|-------------|-------------|
| **blob**    | File contents |
| **tree**    | Directory structure |
| **commit**  | Snapshot of project (points to a tree) |
| **tag**     | Annotates another object |

Each object is stored by its **SHA-1 hash**, split like this:

```plaintext
.git/objects/ab/cdef1234...
```

---

## 🔍 Inspecting Git Objects

### 📌 Get the current commit hash
```bash
git rev-parse HEAD
```

### 📌 Get the object type
```bash
git cat-file -t <hash>
```

### 📌 View contents
```bash
git cat-file -p <hash>
```

---

## 🌳 Tree Structure Example

```bash
git ls-tree HEAD
```

You’ll see tree, blob, and file modes like:
```plaintext
100644 blob abc123…    README.md
040000 tree def456…    src/
```

---

## 📦 Packfiles – Why They Exist

When Git has **many objects**, it compresses them into `.pack` files for efficiency.

Stored in:
```plaintext
.git/objects/pack/
```

### A pack contains:
- `.pack` → Compressed objects
- `.idx`  → Index file to locate objects in the pack

---

## 🧠 Understanding a Packfile

```bash
git verify-pack -v .git/objects/pack/*.idx
```

Output example:
```plaintext
fb057... commit  194 137 12
84368... blob     33  43 149
```

You can then:
```bash
git cat-file -p <hash>
```

---

## 🔄 Full Git Commit Flow

```plaintext
Files → blobs → tree (folder) → commit → branch → HEAD
```

---

## 📚 References

- [Pro Git Book – Git Internals](https://git-scm.com/book/en/v2/Git-Internals)
- Git Commands: `cat-file`, `rev-parse`, `ls-tree`, `verify-pack`


# 😮‍💨
