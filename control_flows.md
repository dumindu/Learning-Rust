# Control Flows

* **if - else if - else**

```
let team_size = 7;
if team_size < 5 {
    println!("Small");
} else if team_size < 10 {
    println!("Medium");
} else {
    println!("Large");
}


let is_below_eighteen = if team_size < 18 { true } else { false };
```

🌟 **Return data type should be same on each block, when using this as an expression.**


* **match**

```
let tshirt_width = 20;
let tshirt_size = match tshirt_width {
    16 => "S", // check 16
    17 | 18 => "M", // check 17 and 18
    19 ... 21 => "L", // check from 19 to 21
    22 => "XL",
    _ => "Not Available",
};


let is_allowed = false;
let list_type = match is_allowed {
    true => "Full",
    false => "Restricted"
    // no default/ _ condition can be skipped 
    // Because data type of is_allowed is boolean and all possibilities checked on conditions 
};
```


* **while**

```
let mut a = 1;
while a <= 10 { 
	println!("Current value : {}", a);
	a += 1; //no ++ or -- on Rust
}

// Usage of break and continue
let mut b = 0;
while b < 5 {
	if b == 0 { 
		println!("Skip value : {}", b);
		b += 1;
		continue;
	} else if b == 2 {
		println!("Break At : {}", b);
		break;
	}
	println!("Current value : {}", b);
	b += 1;
}

// Outer break
let mut c1 = 1;
'outer_while: while c1 < 6 { //set label outer_while
	let mut c2 = 1;
	'inner_while: while c2 < 6 { 
		println!("Current Value : [{}][{}]", c1, c2);
		if c1 == 2 && c2 == 2 { break 'outer_while; } //kill outer_while
		c2 += 1;
	}
	c1 += 1;
}
```


* **loop**

```
loop {
	println!("Loop forever!");
}

// Usage of break and continue
let mut a = 0;
loop {
	if a == 0 {
		println!("Skip Value : {}", a);
		a += 1;
		continue;
	} else if a == 2 {
		println!("Break At : {}", a);
		break;
	}
	println!("Current Value : {}", a);
	a += 1;
}

// Outer break
let mut b1 = 1;
'outer_loop: loop { //set label outer_loop
  let mut b2 = 1;
  'inner_loop: loop {
    println!("Current Value : [{}][{}]", b1, b2);
    if b1 == 2 && b2 == 2 {
        break 'outer_loop; // kill outer_loop
    } else if b2 == 5 {
    	break;
    }
    b2 += 1;
  }
  b1 += 1;
}
```


* **for**

```
for a in 0..10 { //(a = 1; a <11; a++)
  println!("Current value : {}", a);
}

// Usage of break and continue
for b in 0..6 {
  if b == 0 {
    println!("Skip Value : {}", b);
    continue;
  } else if b == 2 {
    println!("Break At : {}", b);
    break;
  }
  println!("Current value : {}", b);
}

// Outer break
'outer_for: for c1 in 1..6 { //set label outer_for
  'inner_for: for c2 in 1..6 {
    println!("Current Value : [{}][{}]", c1, c2);
    if c1 == 2 && c2 == 2 { break 'outer_for; } //kill outer_for
  }
}


// Working with arrays/vectors
let group : [&str; 4] = ["Mark", "Larry", "Bill", "Steve"];

for n in 0..group.len() { //group.len() = 4 -> 0..4 👎 check group.len()on each iteration
  println!("Current Person : {}", group[n]);
}

for person in group.iter() { //👍 group.iter() turn the array into a simple iterator
  println!("Current Person : {}", person);
}
```
