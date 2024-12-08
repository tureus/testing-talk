### Testing, testing

1. Motivate the need for tests
2. Show how Rails makes tests plesasant
3. Examples in a hypothetical rails app

---

### A toy's story

  1. Inject plastic, let it cool, pop it out, inspect visually
  2. Separate parts from the mold, shave off snap points, inspect visually
  3. Paint parts, dry
  4. Clip parts together, screw tight
  5. Construct cardboard box with clear window
  6. Put toy in the box, zip tied to be presentable
  7. Pack crate, wrap in plastic, slap on "no razer blades" stickers
  8. Send crate off on a boat
  9. Hope for the best!

---

<img src="assets/gifs/red-transformer-on-white.gif"/>

---

### A toy's story cont.

The box arrives on the US shores and the 35% tarrifs are paid by the importer.

The inspector validates the factory's work.

---

### A toy's story cont.

Visual inspection

   1. Got the right number of toys?
   2. The packages haven't been soaked or otherwise damaged

---

### A toy's story cont.

Quality can be checked through random sampling. Take 10 units from each batch of 1000

   1. Easy to unbox the toy? Does the collector's seal break?
   2. Does the toy's paint looks good? You can tell it's Optimus Prime and not Nemesis Prime?
   3. Does the truck roll?
   4. Can you perform a transform?
   5. Does Optimus Prime hold his Ion Blaster correctly? Does the toy hold a pose?

---

### A toy's story cont.

The tested unit is no longer suitable for sale because the seal is broken. We will not test every unit because then there'd be nothing to sell.

Any issues that reach the kids will become KMart's problem. KMart can refer to the purchase contract to work out reimbursement.

---

### A toy's story cont.

  Q: How does a manfuacturer know that each transform can actually transform from truck to autobot?

  A: They don't! They set up a process to address known sources of defects at every step of the way and routinely train and assess their staff to make sure the process is followed

---

### A toy's story cont.

  Q: Which step in manufacturing is the most economical for addressing systemic issues?

  A: You tell me 😏

---

### A toy's story cont.

  Q: What's the best way to feed changes through the system?

  A: Again, you tell me 😏

---

### A toy's story cont.

  Q: Why does the end quality matter?

  A: Again, you tell me 😏

---

 # Insert gif of Lucy eating chocolates

---

### Metaphysical applications

How does this hypothetical apply to the craft production of the modern software developer?

Have you ever experienced a bug in software?

How did it make you feel? Do some companies have a better reputation than others? Are you willing to pay a premium for it?

---

### What is quality? Cont.

 * An ethos
   * We take a professional responsibility for what we put out in to the world
   * It's gotta be "good" or what are we even doing
   * We don't throw code over a wall and hope for the best, we care that what we deliver works for our end users and doesn't bring shame to our family name

---

### What is quality? Cont.

 * A methodology
   * A consistent, reproducible process
   * Change is the only constant, we improve our process whenever we can
   * Measurable outcomes
   * Prevention is our philosphy
   * Detection is our backup

---

### Model View Controller architecture

A successful attempt at unifying the construction of database-driven, server-side rendered web apps

I have an idea for Feature X, what part of the app would be reponsible for that? 🤔

---

### MVC Cont.

Each layer has a specific role

Model: data and business logic. Guarantees the database is in accordance with the developer's wishes
View: present the data, build forms for new data. doesn't load data directly
Controller: load data, confirms through models that data looks good, and sends users from one part of the app to another

---

### Testing Models

```ruby
# app/models/user.rb
class User < ActiveRecord::Base
end
```

```ruby
# db/schema.rb
ActiveRecord::Schema[7.0].define(version: 2024_12_10_060000) do
  create_table "users", id: :serial, force: :cascade do |t|
    t.string "email"
    t.string "first_name"
    t.string "last_name"
  end
end
```

---

A test is like a bouncing a ball against a wall, the wall is your app, the test is the ball.

Generate a set of pictures showing the same wall copied many times and a ball having different paths. Each test should be "one bounce" to keep it easy to read and follow, if possible.
