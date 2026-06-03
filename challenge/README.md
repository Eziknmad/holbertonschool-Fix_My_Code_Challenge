# Fix My Code - Challenge

## Description

`Fix my code` is a project where we jump into an existing code base and fix it! Sometimes the language will be familiar, sometimes not. The goal is not to recode everything — just fix the bugs.

## Tasks

### 0. FizzBuzz — `0-fizzbuzz.py`

**Bug:** The `FizzBuzz` condition (`i % 3 == 0 and i % 5 == 0`) was placed after the `Fizz` condition (`i % 3 == 0`), so it was never reached. Numbers divisible by both 3 and 5 (e.g., 15) incorrectly printed `Fizz`.

**Fix:** Moved the `FizzBuzz` check to the top of the if/elif chain.

### 1. Print square — `1-print_square.js`

**Bug:** `parseInt(process.argv[2], 16)` parsed the argument in base 16 (hexadecimal). Passing `10` produced a 16×16 square instead of 10×10.

**Fix:** Changed the radix from `16` to `10`.

### 2. Sort — `2-sort.rb`

**Bug:** `result.insert(i - 1, i_arg)` inserted the element one position too early. When `i = 0`, `i - 1 = -1` inserts at the end of the array in Ruby, breaking the ascending sort.

**Fix:** Changed `i - 1` to `i`.

### 3. User password — `3-user.py`

**Bug 1:** The password setter used `self._password` (single underscore) instead of `self.__password` (double underscore), so the password was never stored in the private attribute.

**Bug 2:** `is_valid_password` compared the hash using `.upper()` while the stored hash used `.lower()`, causing all password validations to fail.

**Fix:** Corrected `self._password` → `self.__password` and `.upper()` → `.lower()`.

### 4. Double linked list — `4-delete_dnodeint/delete_dnodeint_at_index.c`

**Bug 1:** `(*head)->prev->prev = (*head)->prev` set the previous node's `prev` pointer to itself instead of updating its `next` pointer to skip the deleted node.

**Bug 2:** After calling `free(*head)`, the code accessed `(*head)->next` — a use-after-free (undefined behavior).

**Fix:** Saved `prev_node` and `next_node` before freeing, then correctly wired `prev_node->next = next_node` and `next_node->prev = prev_node`.

## Repository

- GitHub repository: `holbertonschool-Fix_My_Code_Challenge`
- Directory: `challenge`
