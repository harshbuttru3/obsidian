# singly Linked list :
### **Algorithm: Insert at Beginning of Singly Linked List**

**Input:** Value `data` to insert  
**Output:** Linked list with the new node at the beginning

---

1. **Create a New Node**
    
    - Allocate memory for a new node.
        
    - Set `new_node.data = data`.
        
2. **Point New Node to Current Head**
    
    - Set `new_node.next = head`.
        
3. **Update Head Pointer**
    
    - Set `head = new_node`.
        
4. **End**
    

### **Pseudocode:**



```
function insertAtBeginning(head, data): 
new_node = createNode()  
new_node.data = data
new_node.next = head 
head = new_node     
return head
```


---
## ✅ 1. Insertion at the End of a Linked List

### **Algorithm:**

**Input:** `head` (pointer to the first node), `data` (value to insert)  
**Output:** Linked list with new node at the end

1. Create a new node and assign `data` to it.
    
2. Set `new_node->next = NULL`.
    
3. If `head == NULL`, set `head = new_node` (empty list case).
    
4. Else:
    
    - Initialize `temp = head`.
        
    - Traverse till `temp->next != NULL`.
        
    - Set `temp->next = new_node`.
        
5. Return `head`.
    

---

### **Pseudocode:**

```
function insertAtEnd(head, data):
    new_node = createNode()
    new_node.data = data
    new_node.next = NULL

    if head == NULL:
        head = new_node
    else:
        temp = head
        while temp.next != NULL:
            temp = temp.next
        temp.next = new_node

    return head

```

---

## ✅ 2. Insertion at Any Position

### **Algorithm:**

**Input:** `head`, `data`, `position` (1-based index)  
**Output:** Linked list with `data` inserted at `position`

1. Create a new node and assign `data` to it.
    
2. If `position == 1`:
    
    - Set `new_node->next = head`.
        
    - Set `head = new_node`.
        
3. Else:
    
    - Initialize `temp = head`.
        
    - Loop from `i = 1` to `position - 2`:
        
        - Move `temp = temp->next`.
            
        - If `temp == NULL`, report "Invalid position".
            
    - Set `new_node->next = temp->next`.
        
    - Set `temp->next = new_node`.
        
4. Return `head`.
    

---

### **Pseudocode:**

```pseudocode
function insertAtPosition(head, data, position):
    new_node = createNode()
    new_node.data = data

    if position == 1:
        new_node.next = head
        head = new_node
    else:
        temp = head
        for i from 1 to position - 2:
            if temp == NULL:
                print "Invalid position"
                return head
            temp = temp.next

        new_node.next = temp.next
        temp.next = new_node

    return head


```


---

## ✅ Traversal of Singly Linked List

### **Goal:**

Visit each node in the list and perform an action (like printing the data).

---

### **Algorithm:**

**Input:** `head` (pointer to the first node)  
**Output:** All node values (e.g., printed to console)

1. Initialize a temporary pointer: `temp = head`.
    
2. While `temp != NULL`:
    
    - Access/print `temp->data`.
        
    - Move `temp = temp->next`.
        
3. End.
    

---

### **Pseudocode:**

```
function traverseLinkedList(head):
    temp = head
    while temp != NULL:
        print temp.data
        temp = temp.next

```


---

## ✅ 1. Deletion from the Beginning

### **Algorithm:**

**Input:** `head`  
**Output:** Updated head after deleting the first node

1. If `head == NULL`:
    
    - Print "List is empty", return `head`.
        
2. Set `temp = head`.
    
3. Set `head = head->next`.
    
4. Free memory of `temp`.
    
5. Return `head`.
    

---

### **Pseudocode:**

```
function deleteFromBeginning(head):
    if head == NULL:
        print "List is empty"
        return head

    temp = head
    head = head.next
    free(temp)

    return head

```

---

## ✅ 2. Deletion from the End

### **Algorithm:**

**Input:** `head`  
**Output:** Updated head after deleting the last node

1. If `head == NULL`:
    
    - Print "List is empty", return `head`.
        
2. If `head->next == NULL`:
    
    - Free `head`, set `head = NULL`, return.
        
3. Initialize `temp = head`.
    
4. While `temp->next->next != NULL`:
    
    - Move `temp = temp->next`.
        
5. Free `temp->next`, set `temp->next = NULL`.
    
6. Return `head`.
    

---

### **Pseudocode:**

```
function deleteFromEnd(head):
    if head == NULL:
        print "List is empty"
        return head

    if head.next == NULL:
        free(head)
        return NULL

    temp = head
    while temp.next.next != NULL:
        temp = temp.next

    free(temp.next)
    temp.next = NULL

    return head

```
---

## ✅ 3. Deletion from a Specific Position

### **Algorithm:**

**Input:** `head`, `position` (1-based index)  
**Output:** Updated head after deletion

1. If `position == 1`:
    
    - Use deletion from beginning.
        
2. Initialize `temp = head`.
    
3. Loop from `i = 1` to `position - 2`:
    
    - If `temp == NULL or temp->next == NULL`:
        
        - Print "Invalid position", return `head`.
            
    - Move `temp = temp->next`.
        
4. Set `toDelete = temp->next`.
    
5. Set `temp->next = toDelete->next`.
    
6. Free `toDelete`.
    
7. Return `head`.
    

---

### **Pseudocode:**
```
function deleteFromPosition(head, position):
    if position == 1:
        return deleteFromBeginning(head)

    temp = head
    for i from 1 to position - 2:
        if temp == NULL or temp.next == NULL:
            print "Invalid position"
            return head
        temp = temp.next

    toDelete = temp.next
    temp.next = toDelete.next
    free(toDelete)

    return head

```
---
## ✅ Searching in a Singly Linked List

### **Goal:**

Find whether a node with a given value exists in the list, and optionally return its position.

---

### **Algorithm:**

**Input:** `head`, `key` (value to search for)  
**Output:** Position of the node if found, else -1

1. Initialize `temp = head` and `pos = 1`.
    
2. While `temp != NULL`:
    
    - If `temp.data == key`, return `pos`.
        
    - Move `temp = temp.next`, increment `pos++`.
        
3. If loop ends without finding `key`, return -1.
    

---

### **Pseudocode:**
```
function search(head, key):
    temp = head
    pos = 1

    while temp != NULL:
        if temp.data == key:
            return pos
        temp = temp.next
        pos = pos + 1

    return -1  // key not found

```
# Doubly linked list: 
A **doubly linked list** is a type of linked list in which each node contains **three parts**:

1. `data` – the value stored in the node
    
2. `prev` – a pointer to the **previous node**
    
3. `next` – a pointer to the **next node**
    

This allows traversal in **both directions** (forward and backward), unlike a singly linked list which only moves forward.
## ✅ 1. Traversal in a Doubly Linked List

### 🔸 **Forward Traversal**

### **Algorithm:**

**Input:** `head` (pointer to first node)  
**Output:** Visit all nodes from head to tail

1. Initialize `temp = head`.
    
2. While `temp != NULL`:
    
    - Print/access `temp.data`.
        
    - Move to next: `temp = temp.next`.
        

### **Pseudocode:**
```
function traverseForward(head):
    temp = head
    while temp != NULL:
        print temp.data
        temp = temp.next

```

---

### 🔸 **Backward Traversal**

### **Algorithm:**

**Input:** `tail` (pointer to last node)  
**Output:** Visit all nodes from tail to head

1. Initialize `temp = tail`.
    
2. While `temp != NULL`:
    
    - Print/access `temp.data`.
        
    - Move to previous: `temp = temp.prev`.
        

### **Pseudocode:**
```
function traverseBackward(tail):
    temp = tail
    while temp != NULL:
        print temp.data
        temp = temp.prev

```
---

## ✅ 2. Insertion in Doubly Linked List

### 🔸 **Insertion at Beginning**

### **Algorithm:**

1. Create `new_node` and set `new_node.data = data`.
    
2. Set `new_node.prev = NULL` and `new_node.next = head`.
    
3. If `head != NULL`, set `head.prev = new_node`.
    
4. Set `head = new_node`.
    

### **Pseudocode:**
```
function insertAtBeginning(head, data):
    new_node = createNode()
    new_node.data = data
    new_node.prev = NULL
    new_node.next = head

    if head != NULL:
        head.prev = new_node

    head = new_node
    return head

```

---

### 🔸 **Insertion at End**

### **Algorithm:**

1. Create `new_node`, set `new_node.data = data`, `new_node.next = NULL`.
    
2. If `head == NULL`, set `new_node.prev = NULL`, `head = new_node`, return.
    
3. Traverse to the last node: `temp = head`, while `temp.next != NULL`, `temp = temp.next`.
    
4. Set `temp.next = new_node`, `new_node.prev = temp`.
    

### **Pseudocode:**
```
function insertAtEnd(head, data):
    new_node = createNode()
    new_node.data = data
    new_node.next = NULL

    if head == NULL:
        new_node.prev = NULL
        head = new_node
        return head

    temp = head
    while temp.next != NULL:
        temp = temp.next

    temp.next = new_node
    new_node.prev = temp

    return head

```

---

### 🔸 **Insertion at a Specific Position**

### **Algorithm:**

**Input:** `head`, `data`, `position`

1. If `position == 1`, use insertAtBeginning.
    
2. Create `new_node`, set `new_node.data = data`.
    
3. Traverse to `temp` at position `position - 1`.
    
4. Set `new_node.next = temp.next`, `new_node.prev = temp`.
    
5. If `temp.next != NULL`, set `temp.next.prev = new_node`.
    
6. Set `temp.next = new_node`.
    

### **Pseudocode:**
```
function insertAtPosition(head, data, position):
    if position == 1:
        return insertAtBeginning(head, data)

    new_node = createNode()
    new_node.data = data

    temp = head
    for i from 1 to position - 2:
        if temp == NULL:
            print "Invalid position"
            return head
        temp = temp.next

    new_node.next = temp.next
    new_node.prev = temp

    if temp.next != NULL:
        temp.next.prev = new_node

    temp.next = new_node

    return head

```
---
## ✅ 1. Deletion from the Beginning

### **Algorithm:**

**Input:** `head`  
**Output:** Head after deleting the first node

1. If `head == NULL`, return (empty list).
    
2. Set `temp = head`.
    
3. Set `head = head.next`.
    
4. If `head != NULL`, set `head.prev = NULL`.
    
5. Free `temp`.
    
6. Return `head`.
    

---

### **Pseudocode:**

```
function deleteFromBeginning(head):
    if head == NULL:
        print "List is empty"
        return head

    temp = head
    head = head.next

    if head != NULL:
        head.prev = NULL

    free(temp)
    return head

```

---

## ✅ 2. Deletion from the End

### **Algorithm:**

**Input:** `head`  
**Output:** Head after deleting the last node

1. If `head == NULL`, return.
    
2. If `head.next == NULL`:
    
    - Free `head`, return `NULL`.
        
3. Traverse to the last node: `temp = head`, while `temp.next != NULL`, move `temp = temp.next`.
    
4. Set `temp.prev.next = NULL`.
    
5. Free `temp`.
    
6. Return `head`.
    

---

### **Pseudocode:**

```
function deleteFromEnd(head):
    if head == NULL:
        print "List is empty"
        return head

    if head.next == NULL:
        free(head)
        return NULL

    temp = head
    while temp.next != NULL:
        temp = temp.next

    temp.prev.next = NULL
    free(temp)

    return head

```

---

## ✅ 3. Deletion from a Specific Position

### **Algorithm:**

**Input:** `head`, `position` (1-based)  
**Output:** Head after deleting node at that position

1. If `position == 1`, use `deleteFromBeginning`.
    
2. Traverse to the `temp` node at position `position`.
    
3. If `temp == NULL`, return (invalid position).
    
4. Set `temp.prev.next = temp.next`.
    
5. If `temp.next != NULL`, set `temp.next.prev = temp.prev`.
    
6. Free `temp`.
    
7. Return `head`.
    

---

### **Pseudocode:**
```
function deleteFromPosition(head, position):
    if position == 1:
        return deleteFromBeginning(head)

    temp = head
    for i from 1 to position - 1:
        if temp == NULL:
            print "Invalid position"
            return head
        temp = temp.next

    if temp.prev != NULL:
        temp.prev.next = temp.next

    if temp.next != NULL:
        temp.next.prev = temp.prev

    free(temp)
    return head

```

## ✅ Searching in a Doubly Linked List

### **Goal:**

Find whether a node with a given value exists in the list, and optionally return its position.

---

### **Algorithm:**

**Input:** `head`, `key` (value to search for)  
**Output:** Position of the node if found, else -1

1. Initialize `temp = head` and `pos = 1`.
    
2. While `temp != NULL`:
    
    - If `temp.data == key`, return `pos`.
        
    - Move `temp = temp.next`, increment `pos++`.
        
3. If loop ends, return -1 (key not found).
    

---

### **Pseudocode:**

```
function search(head, key):
    temp = head
    pos = 1

    while temp != NULL:
        if temp.data == key:
            return pos
        temp = temp.next
        pos = pos + 1

    return -1  // key not found

```

---

### 🔎 Example Use:

If `key = 25` and it's the third node in the list, the function returns `3`.  
If `key = 99` and not in the list, it returns `-1`.
# Circular Linked list : 

## ✅ Searching in a Circular Singly Linked List

### **Goal:**

Find whether a node with a given value exists in the circular linked list, and optionally return its position.

---

### **Algorithm:**

**Input:** `head`, `key` (value to search for)  
**Output:** Position of the node if found, else -1

1. If `head == NULL`, return -1 (list is empty).
    
2. Initialize `temp = head` and `pos = 1`.
    
3. Repeat:
    
    - If `temp.data == key`, return `pos`.
        
    - Move `temp = temp.next`, increment `pos++`.
        
4. Until `temp == head` (we have traversed the whole circular list).
    
5. If key not found, return -1.
    

---
### Pseudocode:
```
function searchCircularList(head, key):
    if head == NULL:
        return -1  // empty list

    temp = head
    pos = 1

    do:
        if temp.data == key:
            return pos
        temp = temp.next
        pos = pos + 1
    while temp != head

    return -1  // key not found

```
## 1. **Traversal**

### Algorithm:

- Start at `head`.
    
- Visit each node and move to `next`.
    
- Stop when you return back to `head`.
    

### Pseudocode:


```
function traverse(head):
    if head == NULL:
        return

    temp = head
    do:
        print temp.data
        temp = temp.next
    while temp != head

```

---

## 2. **Insertion**

### a) At Beginning

- Create new node.
    
- If list empty, point new node to itself, set `head = new_node`.
    
- Else, find last node, update its next to new_node.
    
- Point new_node's next to current head.
    
- Update `head = new_node`.
    

### Pseudocode:

```
function insertAtBeginning(head, data):
    new_node = createNode(data)
    if head == NULL:
        new_node.next = new_node
        head = new_node
        return head

    temp = head
    while temp.next != head:
        temp = temp.next

    temp.next = new_node
    new_node.next = head
    head = new_node

    return head

```

---

### b) At End

- Create new node.
    
- If list empty, point new node to itself, set `head = new_node`.
    
- Else, find last node, set last node's next to new_node.
    
- Point new_node's next to head.
    

### Pseudocode:

```
function insertAtEnd(head, data):
    new_node = createNode(data)
    if head == NULL:
        new_node.next = new_node
        head = new_node
        return head

    temp = head
    while temp.next != head:
        temp = temp.next

    temp.next = new_node
    new_node.next = head

    return head

```
---

### c) At Specific Position (1-based)

- If position == 1, insert at beginning.
    
- Else, traverse to `(position - 1)` node.
    
- Insert new node after that node by adjusting next pointers.
    

### Pseudocode:
```
function insertAtPosition(head, data, position):
    if position == 1:
        return insertAtBeginning(head, data)

    new_node = createNode(data)
    temp = head
    for i from 1 to position - 2:
        temp = temp.next
        if temp == head:
            print "Invalid position"
            return head

    new_node.next = temp.next
    temp.next = new_node

    return head

```
---

## 3. **Deletion**

### a) From Beginning

- If list empty, do nothing.
    
- If only one node, delete it and set head = NULL.
    
- Else, find last node, update its next to `head.next`.
    
- Delete old head.
    
- Update `head = head.next`.
    

### Pseudocode:
```
function deleteFromBeginning(head):
    if head == NULL:
        return NULL

    if head.next == head:
        free(head)
        return NULL

    temp = head
    last = head
    while last.next != head:
        last = last.next

    last.next = head.next
    head = head.next
    free(temp)

    return head

```

---

### b) From End

- If list empty, do nothing.
    
- If only one node, delete it and set head = NULL.
    
- Else, traverse to second last node.
    
- Delete last node and update second last’s next to head.
    

### Pseudocode:

```
function deleteFromEnd(head):
    if head == NULL:
        return NULL

    if head.next == head:
        free(head)
        return NULL

    temp = head
    while temp.next.next != head:
        temp = temp.next

    free(temp.next)
    temp.next = head

    return head

```
---

### c) From Specific Position

- If position == 1, delete from beginning.
    
- Else, traverse to `(position - 1)` node.
    
- Adjust pointers to remove node at position.
    
- Free deleted node.
    

### Pseudocode:
```
function deleteFromPosition(head, position):
    if head == NULL:
        return NULL

    if position == 1:
        return deleteFromBeginning(head)

    temp = head
    for i from 1 to position - 2:
        temp = temp.next
        if temp.next == head:
            print "Invalid position"
            return head

    toDelete = temp.next
    temp.next = toDelete.next
    free(toDelete)

    return head

```

## 5. **Length/Count**

- Traverse the list counting nodes until return to head.
    

### Pseudocode:
```
function length(head):
    if head == NULL:
        return 0

    count = 0
    temp = head
    do:
        count = count + 1
        temp = temp.next
    while temp != head

    return count

```
