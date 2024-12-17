# Awesome Rust

I learn Rust by reading [The Rust Programming Language](http://doc.rust-lang.org/book/index.html) (aka. TRPL) book.

This is my ~~mind map and~~ collection of resources for learning Rust in early 2019.

I plan to continuously update this list if time allows in future.
I will move this into its own GitHub repo or something more permanent when this grow.

---

## Notes

My notes while working through TRPL.

**Programming paradigm:** functional, imperative, structured, generic, concurrent

**Rust focus:** type and memory safety, precision, concurrency, performance, reliability

Rust enforces memory safety. Compile time memory safety guarantees protects us from:

- Uninitialized variables
- Use-after-free (UAV)
- Double-frees
- Exception due to NULL pointers (Rust does not have NULL)
- Impossible to forget to lock the mutex
- Data races between threads
- _Mostly_ no memory leaks
- Iterator invalidation

In the safe subset of Rust, there's no undefined behavior at runtime:

- Integer overflow is defined
- Array access is bounds checked

Rust is modern — built with the experience learned in the past 40 years of programming languages.

Modern language features:
- Generics
- Enums and pattern matching
- No overhead FFI

Modern tooling:
- Great compiler errors
- Built-in dependency manager
- Built-in support for testing

---

## Getting Help

- [Users forum](https://users.rust-lang.org/) - official forum
- [Internals forum](https://internals.rust-lang.org/) - official forum
- [The #beginners channel on Discord](https://discord.gg/rust-lang)

## Learn Rust

- [Get started with Rust](https://www.rust-lang.org/learn) - **Official learning resources**.
- [Rust Cookbook](https://rust-lang-nursery.github.io/rust-cookbook/) - A collection of simple examples that demonstrate good practices to accomplish common programming tasks, using the crates of the Rust ecosystem.
- [Rust by Example](https://doc.rust-lang.org/stable/rust-by-example/) - A collection of runnable examples that illustrate various Rust concepts and standard libraries.
- [Learn Rust With Entirely Too Many Linked Lists](https://rust-unofficial.github.io/too-many-lists/)
- https://github.com/rust-lang/rustlings - Small exercises to get you used to reading and writing Rust code!
- [Tour of Rust](https://tourofrust.com/) - A step by step guide through the features of the Rust programming language.
- [A half-hour to learn Rust](https://fasterthanli.me/blog/2020/a-half-hour-to-learn-rust/) - 'similar' style to "Learn X in Y Minutes". It covers variable bindings, pattern matching, immutability, references, lifetimes, borrow rules, structs, traits, enums, generics, closures, and more.
- [Read Rust: Getting Started](https://readrust.net/getting-started) - Introductory posts, guides and tutorials for getting started with Rust.
- [Learning Rust](https://learning-rust.github.io/) - Rust programming language tutorials.
- [Rust-101](https://www.ralfj.de/projects/rust-101/) - A tutorial for the Rust language.
- https://github.com/learning-rust/site - Rust Programming Language Tutorials for Everyone!
- [Comprehensive Rust 🦀](https://google.github.io/comprehensive-rust/) - This is the Rust course used by the Android team at Google. It provides you the material to quickly teach Rust to everyone. The course covers the full spectrum of Rust, from basic syntax to advanced topics like generics and error handling. It also includes Android-specific content on the last day.

### Videos

Rust stream on YouTube and/or Twitch:

- [Jon Gjengset's stream on Rust](https://www.youtube.com/channel/UC_iD0xppBwwsrM9DegC5cQQ) - I first discovered Jon's stream while looking at [Noria](https://github.com/mit-pdos/noria) data-flow for high-performance web apps. Jon's stream covers mostly advanced concepts in Rust but not until recently (2020) where he started to covers more "advanced beginners" stuffs.
- [Ryan Levick's "advanced beginners" stream on Rust](https://youtu.be/2mwwYbBRJSo) who are familiar with the concepts of ownership, closures and threads but don't yet have a firm grip on them.
- [Visualizing memory layout of Rust's data types](https://www.youtube.com/watch?v=rDoqT-a6UFg)
- [Intorust screencasts](http://intorust.com/) by Niko Matsakis.

## Books

- [Rust for Rustaceans](https://www.reddit.com/r/rust/comments/nq3pxh/new_rust_book_rust_for_rustaceans_by_jon_gjengset/) by Jon Gjengset - a book that covers the next steps of Rust after TRPL/"the book". The book is written for people who are already familiar with Rust. The idea is that you read The Rust Programming Language (TRPL) first, play around with Rust for a bit on your own, maybe start using it "for real", and then pick this up to hone your skills. It is fairly fast paced, but is still has a good amount of low level details. (TLDR; if you're comfortable in Rust, this book is the next step up for intermediate developers.)
- [Rust in Action](https://www.manning.com/books/rust-in-action) by Tim McNamara - Systems programming concepts and techniques.
  - [Book launch announcement](https://www.reddit.com/r/rust/comments/bthr5n/rust_in_action_by_ts_mcnamara_published_by/)
- [Programming Rust](https://www.oreilly.com/library/view/programming-rust-2nd/9781492052586/) by Jim Blandy, Jason Orendorff, Leonora F. S. Tindall - This revised, second edition covers the Rust 2021 Edition. It expands on many concepts in TRPL book. I like that it explains the **memory layout of common Rust data structures**.
- [The Rustonomicon book](https://doc.rust-lang.org/nomicon/meet-safe-and-unsafe.html) - Meet Safe and Unsafe.
- https://github.com/psibi/rust-book-summary - Summary of the Rust book.

## Presentations and Talks

- [Rust: A Language for the Next Forty Years](https://is.gd/rust40) by Carol Nichols - A talk about Rust's safety and stability. And a little bit about railroads.
- [Learning systems programming with Rust](https://jvns.ca/blog/2016/09/11/rustconf-keynote/) - Closing keynote at the first RustConf 2016 by Julia Evans.

## Cheat sheet

- https://cheats.rs/

## Libraries

Useful libraies. Some created by Rust core members.

[Blessed](https://blessed.rs/) - An unofficial guide to the Rust ecosystem.

[Not-Yet-Awesome Rust](https://github.com/not-yet-awesome-rust/not-yet-awesome-rust) - A curated list of Rust code and resources that do NOT exist yet, but would be beneficial to the Rust community.

### Other Crates

- https://github.com/rayon-rs/rayon
- https://github.com/brson/stdx

<details>
<summary>See more</summary>

- https://github.com/valebes/rsClock
- https://github.com/rusoto/rusoto
- https://github.com/bbqsrc/cargo-ndk
- https://github.com/Peltoche/lsd
- https://github.com/vi/websocat
- https://github.com/theotherphil/imagecli
- https://github.com/CianLR/mazegen-rs
- https://github.com/RustAudio
- https://github.com/housleyjk/ws-rs
- https://github.com/getzola/zola - Static site engine. An alternative to Hugo and Jekyll.
- https://github.com/habitat-sh/habitat
- https://github.com/starship/starship
- https://github.com/Edu4rdSHL/findomain
- https://github.com/TheAlgorithms/Rust
- https://github.com/jedisct1/rust-bloom-filter
- https://github.com/rustodon/rustodon
- https://github.com/fishinabarrel/linux-kernel-module-rust
- https://github.com/dani-garcia/bitwarden_rs
- https://github.com/TimelyDataflow/differential-dataflow - Similar to Noria.
- https://github.com/pemistahl/grex
- https://github.com/Rigellute/spotify-tui

- https://github.com/getsentry/symbolicator - using actix-web for their symbolicator project

- https://github.com/sfackler/rust-postgres-macros
- https://github.com/nagisa/rust_libloading

- https://github.com/Geal/nom

- https://github.com/jaredly/veoluz
- https://github.com/CianLR/mazegen-rs
- https://github.com/alexcrichton/cargo-wasi
- https://github.com/google/evcxr

- https://github.com/agersant/polaris
- https://github.com/XAMPPRocky/tokei

<!-- DONE -->
- https://github.com/sfackler/rust-antidote - Poison-free versions of the Rust standard library `Mutex` and `RwLock` types.

<!-- DONE READING -->
- https://github.com/cloudflare/boringtun

<!-- NICE -->
- https://github.com/valeriansaliou/sonic
- https://github.com/toshi-search/Toshi - An Elasticsearch competitor written in Rust. <!-- Related: https://news.ycombinator.com/item?id=18895655 -->

<!-- COOL -->
- https://github.com/timberio/vector

</details>
  
#### Programs and Apps

- https://github.com/xi-editor/xi-editor - an example of real-world usage of Rust.
- [Real Time For the Masses (RTFM) framework for ARM Cortex-M microcontrollers](https://github.com/rtfm-rs/cortex-m-rtfm)

#### GUI

Cross-platform, desktop UI:

- https://github.com/anp/moxie
- https://github.com/KenSuenobu/rust-pushrod
- https://github.com/tauri-apps/tauri
- https://github.com/hecrj/iced

## Blogs and Articles

- https://medium.com/@cevans3326/rust-in-2018-lets-fix-where-the-bullet-holes-aren-t-7e94cea0bd53
- [Read Rust](https://readrust.net/) collects interesting posts related to the Rust programming language. <!-- MUST READ -->

  Note-to-self: I found the writer through Mastodon

- Official Posts:
  - https://blog.rust-lang.org/2016/12/22/Rust-1.14.html
  - https://blog.rust-lang.org/2017/05/15/rust-at-two-years.html
  - https://blog.rust-lang.org/2017/05/05/libz-blitz.html
  - https://blog.rust-lang.org/2016/05/16/rust-at-one-year.html
  - https://blog.rust-lang.org/2016/06/30/State-of-Rust-Survey-2016.html

<details>
<summary>See more</summary>

- https://internals.rust-lang.org/t/production-user-research-summary/2530/3
- [Dropbox using Rust in production](https://news.ycombinator.com/item?id=11283688)
- http://aturon.github.io/blog/2015/08/27/epoch/
- http://calculist.org/blog/2015/12/23/neon-node-rust/
- https://blog.skylight.io/rust-means-never-having-to-close-a-socket/
- <!-- DONE --> https://softwareengineeringdaily.com/2018/06/19/rust-networking-with-carl-lerche/
- <!-- DONE --> http://arthurtw.github.io/2014/11/30/rust-borrow-lifetimes.html
  - Discovered: https://medium.com/@ericdreichert/how-i-think-about-rust-lifetimes-83a726aaa846
- https://medium.com/@saschagrunert/a-web-application-completely-in-rust-6f6bdb6c4471
- https://gendignoux.com/blog/2017/09/05/rust-vs-cpp-ocaml-part1.html
- https://kristoff.it/blog/why-go-and-not-rust/
- https://notamonadtutorial.com/sonic-a-minimalist-alternative-to-elasticsearch-written-in-rust-7f3612ecb47b
- [Rust Lifetime Visualization Ideas](https://blog.adamant-lang.org/2019/rust-lifetime-visualization-ideas/)
- [Key Learnings in Rust after 30K Lines of Code (2019)](http://archive.today/JjEJx)
- Production/real-world usage: [The Firecracker virtual machine monitor](https://lwn.net/Articles/775736/)

- https://ngoldbaum.github.io/posts/python-vs-rust-nn/
- https://corecursive.com/013-rust-and-bitter-c-developers-with-jim-blandy/
- [Backdooring Rust crates for fun and profit](https://kerkour.com/rust-crate-backdoor/)
- [Rust Web Survey 2018](https://rustasync.github.io/team/2018/11/28/wg-net-survey.html) <!-- DONE -->

<!-- DONE READING --> 
- https://aws.amazon.com/blogs/opensource/rust-runtime-for-aws-lambda/
- [Comparing Parallel Rust and C++ (parallel-rust-cpp.github.io)](https://news.ycombinator.com/item?id=21469295)

</details>
  
Blogs

- [Manish Goregaokar's blog](https://manishearth.github.io/)
- [Mara's blog](https://blog.m-ou.se/)
- [Steve Klabnik's blog](https://steveklabnik.com/writing)
- [Amos's blog](https://fasterthanli.me/)
- [Yoshua Wuyts's blog](https://blog.yoshuawuyts.com/)
- [Llogiq's blog](https://llogiq.github.io/)
- [Raph Levien’s blog](https://raphlinus.github.io/)
- [Sean McArthur's blog](https://seanmonstar.com/)

## Newsletters

- [This Week in Rust](https://this-week-in-rust.org/)

## Async Rust

- https://github.com/rustasync/areweasyncyet.rs - A website for tracking development progress of `async`/`await` syntax of Rust programming language in the language itself as well as its ecosystem.

## Editor, IDE

https://areweideyet.com/

Things I discovered:

- https://github.com/racer-rust/racer - Rust code completion utility.
- [explaine.rs](https://jrvidal.github.io/explaine.rs/) - An interactive playground to explore the syntax of the Rust code.

## Web Frameworks

Status: https://www.arewewebyet.org/

- https://brandur.org/rust-web
- https://larder.io/blog/larder-links-09-rust-web-frameworks/
- https://github.com/iron/iron
- https://github.com/nickel-org/nickel.rs
- https://github.com/tokio-rs/tokio-minihttp
- https://github.com/trezm/Thruster
- https://github.com/graphql-rust/juniper
- Tower-Web and Warp joint effort
  - Warp on Zeit Now or AWS Lambda: https://zeit.co/blog/introducing-now-rust
- Templates
  - https://github.com/djc/askama

### Actix

- [Actix-web 1.0 – A small, pragmatic, and fast web framework for Rust](https://news.ycombinator.com/item?id=20104619)
- https://www.reddit.com/r/rust/comments/cbn1no/rust_is_leading_most_of_the_techempower_web/
- https://github.com/TechEmpower/FrameworkBenchmarks/issues/4834
- 1.0 summary: https://www.reddit.com/r/rust/comments/bwy99w/actixweb_10_released/eq2t499/
- https://www.reddit.com/r/programming/comments/cbgv6f/rust_async_frameworks_dominate_techempower/
- https://www.reddit.com/r/rust/comments/axy0hp/patterns_to_scale_actixweb_and_diesel/
- https://www.reddit.com/r/rust/comments/ce09id/why_we_need_alternatives_to_actix/
- https://64.github.io/actix/
- Examples:
  - https://github.com/flofriday/thumbcloud
  - https://github.com/ArtRand/kafka-actix-example
  - https://medium.com/meetbitfury/generic-methods-in-rust-how-exonum-shifted-from-iron-to-actix-web-7a2752171388
  - https://blog.approveapi.com/tutorials/rust-actix-web-approveapi-magic-login-link/
- https://render.com/docs/deploy-actix-todo

Actor Model

- https://simplabs.com/blog/2018/06/11/actix/

### Comparison

- https://github.com/flosse/rust-web-framework-comparison#server-frameworks

### Rust and Node.js

<!-- DONE -->
Rust bindings for native Node.js modules:
- https://github.com/neon-bindings/neon

## Rust for Python Programmer

- https://www.reddit.com/r/rust/comments/azit15/i_made_a_super_simple_example_guide_of_how_to/
- https://www.reddit.com/r/rust/comments/abfoe0/my_experience_converting_a_python_library_to_rust/
- https://alantrick.ca/writings/programming/python_to_rust/
- http://lucumr.pocoo.org/2015/5/27/rust-for-pythonistas/

## WebAssembly

WebAssembly (abbrevated a wasm) is an emerging technology.

- <!-- DONE --> https://www.rust-lang.org/what/wasm
- <!-- DONE --> https://blog.mgattozzi.dev/rust-wasm/
- https://github.com/rustwasm

<details>
<summary>See more</summary>

- https://github.com/wasmerio/wasmer
- <!-- DONE --> https://hacks.mozilla.org/2017/02/a-cartoon-intro-to-webassembly/
- https://twitter.com/DasSurma/status/1034138207091187712
- <!-- DONE --> https://medium.com/@robaboukhalil/hit-the-ground-running-with-webassembly-56cf9b2fa35d
- https://dev.to/talentlessguy/let-s-write-frontend-in-go-6ch
- <!-- DONE --> https://v8.dev/blog/emscripten-llvm-wasm
- https://hacks.mozilla.org/2017/09/bootcamps-webassembly-and-computer-vision/
- https://dev.to/sendilkumarn/tiny-go-to-webassembly-5168
- https://github.com/WebAssembly/wabt

Updates from Web teams at Google:

- https://developers.google.com/web/updates/tags/webassembly#emscripting_a_c_library_to_wasm
- https://developers.google.com/web/updates/2018/03/emscripting-a-c-library
- https://developers.google.com/web/updates/2018/10/wasm-threads
- https://developers.google.com/web/updates/2018/04/loading-wasm
- https://developers.google.com/web/updates/2019/01/emscripten-npm

</details>
  
## Rust and Cloud
  
AWS Lambda:

- https://github.com/softprops/lando
- https://github.com/srijs/rust-aws-lambda
  - Related: https://github.com/LegNeato/aws-lambda-events
    - Related: https://github.com/graphql-rust
- https://github.com/softprops/serverless-rust

## Rust on Mobile

Use Rust with Android NDK:

- https://www.reddit.com/r/rust/comments/b14wah/rust_library_for_ios_and_android_native/
- https://users.rust-lang.org/t/rust-on-android-today/17884/12

## Rust Communities

Users of the Rust programming language: https://communitywiki.org/trunk/grab/Rustaceans

### Reddit /r/rust

- https://www.reddit.com/r/rust/comments/b3vw8w/alexis_beingessners_learning_rust_with_entirely/
- https://www.reddit.com/r/rust/comments/cra26t/sonata_100_rust_audio_decoders_media_demuxers_and/
- https://www.reddit.com/r/rust/comments/cysvjh/what_are_some_amazing_softwaresoftware_clones/
- https://www.reddit.com/r/rust/comments/cxmki8/introduction_to_rust_web_applications/
- https://www.reddit.com/r/rust/comments/cm7rje/rust_language_cheat_sheet/

<details>
<summary>See more</summary>

- https://www.reddit.com/r/rust/comments/dbtgr8/accurate_mental_model_for_rusts_reference_types/
- https://www.reddit.com/r/rust/comments/dhbpm9/announcing_displaydoc_a_doc_comment_based_derive/
- https://www.reddit.com/r/rust/comments/dh96ta/zerocopylmdb_would_love_security_and_soundness/
- https://www.reddit.com/r/rust/comments/dh8lev/mullvad_vpn_desktop_and_mobile_app_written_in/
- https://www.reddit.com/r/rust/comments/dfvyzt/announcing_alexandrie_a_modular_alternative_crate/
- https://www.reddit.com/r/rust/comments/dfv8er/alass_2_automatic_lanugageagnostic_subtitle/
- https://www.reddit.com/r/rust/comments/dfei9l/the_node_experiment_exploring_async_basics_with/
- https://www.reddit.com/r/rust/comments/de5hvu/writing_an_os_in_rust_updates_in_september_2019/
- https://www.reddit.com/r/rust/comments/dc5kky/writing_linux_kernel_modules_in_safe_rust_linux/
- https://www.reddit.com/r/rust/comments/di8bh9/paste_a_selfhostable_pastebin_written_in_rust/
- https://www.reddit.com/r/rust/comments/ddhieo/how_cheap_is_a_channel/
- https://www.reddit.com/r/rust/comments/ddul57/fledgeling_rustacean_here_please_provide_feedback/
- https://www.reddit.com/r/rust/comments/ddsqsu/looking_for_medium_sized_project_ideas/
- https://www.reddit.com/r/rust/comments/ddu1dq/announcing_asuran_a_new_deduplicating_archiver/
- https://www.reddit.com/r/rust/comments/ddpuc4/using_rust_for_critical_embedded_software/
- https://www.reddit.com/r/rust/comments/ddtbpm/this_month_in_rust_gamedev_2_september_2019/
- https://www.reddit.com/r/rust/comments/dekxcw/experimental_pure_rust_implementation_of_aesgcm/
- https://www.reddit.com/r/rust/comments/desc3q/dev_time_optimization_part_1_19x_speedup_65_less/
- https://www.reddit.com/r/rust/comments/deyz3h/how_do_rust_references_work/
- https://www.reddit.com/r/rust/comments/dfkwfo/announcing_thiserror_a_convenient_modern/
- https://www.reddit.com/r/rust/comments/dj4pev/asynchronous_destructors/
- https://www.reddit.com/r/rust/comments/djgd2c/middle_school_robotics_lab_im_teaching_uses_the/
- https://www.reddit.com/r/rust/comments/dj8ki0/lemmy_a_reddit_alternative_written_in_rust/
- https://www.reddit.com/r/rust/comments/dj5q1p/rusts_journey_to_asyncawait/
- https://www.reddit.com/r/rust/comments/dj8wo3/bootstrapping_a_5_node_kubernetes_cluster_in_40/

- https://www.reddit.com/r/rust/comments/deyz3h/how_do_rust_references_work/
- https://www.reddit.com/r/rust/comments/dcx0k4/introducing_my_coworker_to_rust_via_the_intorust/
- https://www.reddit.com/r/rust/comments/dcdwur/static_assertions_10/
- https://www.reddit.com/r/rust/comments/dcporr/compile_stress_test/
- https://www.reddit.com/r/rust/comments/dcsc3k/announcing_the_inside_rust_blog/
- https://www.reddit.com/r/rust/comments/djhfkp/need_opinionated_articles_aboutagainst_rust/

- https://www.reddit.com/r/rust/comments/dkck8s/opensource_contributions_stream_rust_tools_and/
- https://www.reddit.com/r/rust/comments/dk8hky/the_rust_ui_working_group/
- https://www.reddit.com/r/rust/comments/dkiuy6/question_about_design_principles_design_patterns/
- https://www.reddit.com/r/rust/comments/dl5klz/video_a_quiet_session_of_rust_refactoring/
- https://www.reddit.com/r/rust/comments/dl1sw2/a_tiny_static_fulltext_search_engine_using_rust/
- https://www.reddit.com/r/rust/comments/dltdmm/spark_implemented_in_rust_with_promising_results/
- https://www.reddit.com/r/rust/comments/dlz3fb/nannou_the_creative_coding_framework_awarded/
- https://www.reddit.com/r/rust/comments/e2ssqr/redox_os_real_hardware_breakthroughs_and_focusing/
- https://www.reddit.com/r/rust/comments/e1jckj/iced_a_crossplatform_gui_library_new_release/
- https://www.reddit.com/r/rust/comments/e217z6/tokio_02_released_roadmap_to_10/
- <!-- TODO --> https://www.reddit.com/r/rust/comments/cwfgqv/announcing_actixraft_raft_distributed_consensus/
    <!-- Question: How does this compare to pingcap/raft-rs? -->
- https://www.reddit.com/r/rust/comments/cldzyt/understanding_rust_through_avl_trees_a_long_intro/
- https://www.reddit.com/r/rust/comments/dorinl/a_call_for_blogs_2020/

</details>

<details>
<summary>Projects for learning</summary>

- Learn Embedded Rust: https://www.reddit.com/r/rust/comments/dj6ylq/rotary_encoders_in_embedded_rust/
- https://www.reddit.com/r/rust/comments/dct3fm/writing_an_http_server_in_rust_part_i/
- https://www.reddit.com/r/rust/comments/dk2km3/i_made_a_nes_emulator_in_rust_using_generators/
- <!-- DONE --> https://www.reddit.com/r/rust/comments/cmra8k/where_to_find_small_rust_todosprojects_to_hack/

</details>

<details>
<summary>A sad day in Rust - related to actix-web debacle</summary>

- https://www.reddit.com/r/rust/comments/eq11t3/a_sad_day_for_rust/
- https://www.reddit.com/r/rust/comments/epoloy/ive_smoketested_rust_http_clients_heres_what_i/
- https://www.reddit.com/r/rust/comments/epszt7/actixnet_unsoundness_patch_is_boring/
- https://www.reddit.com/r/rust/comments/eq5l6s/actixsupportletter/
- https://www.reddit.com/r/rust/comments/eq4xsu/gauging_interest_in_an_actixweb_and_siblings_fork/
- https://www.reddit.com/r/rust/comments/epzukc/actix_web_repository_cleared_by_author_who_says/
- https://www.reddit.com/r/rust/comments/eq0375/what_should_i_choose_in_post_actixweb_era_for_web/
- https://www.reddit.com/r/rust/comments/epo5w3/warp_v02_the_composable_web_server_framework/

</details>

## Systems Programming with Rust

- Operating Systems (Kernel hacking)
  - [Create a small operating system in Rust](https://os.phil-opp.com/) - You can learn Rust by creating a small OS. This is an ongoing blog series. I find this pair well with OS theory from the ["Operating Systems: Three Easy Pieces"](https://pages.cs.wisc.edu/~remzi/OSTEP/) book (a.k.a. the comet book) and [CS-537 class](https://pages.cs.wisc.edu/~remzi/Classes/537/Spring2018/) by Remzi. (If anyone have compared xv6 to Blog OS, please let me know.)
- Low-level Programming (core utilities, tools, emulators, embedded programming)

## Problems and Issues

Problems and issues I encountered.

- Solutions from StackOverflow
  - https://stackoverflow.com/questions/29403920/whats-the-difference-between-use-and-extern
  - https://stackoverflow.com/questions/36604010/how-can-i-build-multiple-binaries-with-cargo

## General

Not so useful knowledge.

- Rust history
  - https://www.reddit.com/r/rust/comments/7qels2/i_wonder_why_graydon_hoare_the_author_of_rust/
  - https://github.com/graydon/rust/wiki/Meetings
- Rust Core team
  - https://github.com/nikomatsakis
  - https://github.com/alexcrichton
  - Graydon Hoare
    - https://www.reddit.com/r/rust/comments/7v5kyk/rust_creator_graydon_hoare_says_current_software/
    - https://thenewstack.io/rust-creator-graydon-hoare-talks-about-security-history-and-rust/
  - ... and more

## Similar Projects

- [Awesome Rust](https://github.com/rust-unofficial/awesome-rust)
- [rust-learning](https://github.com/ctjhoa/rust-learning) - A bunch of links to blog posts, articles, videos, etc for learning Rust.

---

## Learn Rust Again

Stuffs I referenced in Nov 2019 while learning Rust again by reading "The Rust Programmming Language" book.

- Rust for loop odd step
  - https://zsiciarz.github.io/24daysofrust/book/vol1/day2.html
  - https://www.cs.brandeis.edu/~cs146a/rust/doc-02-21-2015/book/compound-data-types.html
- Rust system of ownership Euler
  - https://www.jonathanturner.org/2015/10/lessons-from-first-12-euler-problems-in.html
  - https://hellocode.dev/rust-ownership
- Rust ownership guide / mastering rust ownership / rust ownership kata / rust ownership practice
  - https://words.steveklabnik.com/pointers-in-rust-a-guide
  - [Graphical depiction of ownership and borrowing in Rust](https://www.reddit.com/r/rust/comments/5u6e6f/graphical_depiction_of_ownership_and_borrowing_in/) <!-- TO READ -->
  - [Borrow visualizer for the Rust Language Service](https://internals.rust-lang.org/t/borrow-visualizer-for-the-rust-language-service/4187/1)
- Destructure tuple struct
  - https://learning-rust.github.io/docs/b2.structs.html
- What is Rust Trait
  - https://stevedonovan.github.io/rustifications/2018/09/08/common-rust-traits.html
- Rust match expression and Option enum
  - https://oribenshir.github.io/afternoon_rusting/blog/enum-and-pattern-matching-part-1
- [PostgreSQL Extension in C with Rustlang](https://gist.github.com/ranjanprj/c18f0927ace72cf70b028e02e9f8f6e5)
- Rust crates to use in multithreaded
  - https://stjepang.github.io/2019/01/29/lock-free-rust-crossbeam-in-2019.html
  - ... and many more.
- [Rust at speed — building a fast concurrent database](https://www.reddit.com/r/rust/comments/acucrs/rust_at_speed_building_a_fast_concurrent_database/) <!-- VIDEO, GREAT -->
- Project Idea:
  - [Building an SQL database with 10 Rust beginners](https://lukaskalbertodt.github.io/2015/10/09/building-an-sql-database-with-10-rust-beginners.html) <!-- READING -->
  - [Tutorial: Getting Started with Rust by Building a Tiny Markdown Compiler](https://www.reddit.com/r/rust/comments/dl998z/tutorial_getting_started_with_rust_by_building_a/) <!-- TO READ -->
  - [A Tiny, Static, Full-Text Search Engine using Rust and WebAssembly](https://endler.dev/2019/tinysearch/) <!-- TO READ -->