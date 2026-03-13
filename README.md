mport time

def real_time_binary_search(arr, target):
low = 0
high = len(arr) - 1
step = 1

print(f" Target to find: {target}")
print(f" Sorted List: {arr}")
print("-" * 50)

while low <= high:
# Calculate the middle index
mid = (low + high) // 2
mid_val = arr[mid]

print(f"STEP {step}:")
print(f"  Current Range: Indices [{low} to {high}]")
print(f"  Checking Middle Index {mid} (Value: {mid_val})...", end=" ", flush=True)

# Pause to simulate real-time decision making
time.sleep(1.5)

if mid_val == target:
print(f"\n   MATCH FOUND! {target} is at Index {mid}.")
return mid

elif mid_val < target:
print(f" {target} is LARGER.")
print(f"   Shifting search to the RIGHT half (Indices {mid + 1} to {high}).")
low = mid + 1

else:
print(f" {target} is SMALLER.")
print(f"  Shifting search to the LEFT half (Indices {low} to {mid - 1}).")
high = mid - 1

step += 1
print("-" * 20)

print(f"\n Finished: {target} was not found in the list.")
return -1

# --- Execution ---
# MUST be sorted for Binary Search
sorted_data = [10, 20, 30, 40, 50, 60, 70, 80, 90, 100]
target_number = 70

real_time_binary_search(sorted_data, target_number)



Output:
 Target to find: 70
 Sorted List: [10, 20, 30, 40, 50, 60, 70, 80, 90, 100]
--------------------------------------------------
STEP 1:
Current Range: Indices [0 to 9]
Checking Middle Index 4 (Value: 50)...  70 is LARGER.
Shifting search to the RIGHT half (Indices 5 to 9).
--------------------
STEP 2:
Current Range: Indices [5 to 9]
Checking Middle Index 7 (Value: 80)...  70 is SMALLER.
 Shifting search to the LEFT half (Indices 5 to 6).
--------------------
STEP 3:
Current Range: Indices [5 to 6]
Checking Middle Index 5 (Value: 60)...  70 is LARGER.
 Shifting search to the RIGHT half (Indices 6 to 6).
--------------------
STEP 4:
Current Range: Indices [6 to 6]
Checking Middle Index 6 (Value: 70)...
 MATCH FOUND! 70 is at Index 6.
 
