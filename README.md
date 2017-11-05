<div class="post_region_content note" id="view_quesiton_note">
        
<h1 data-pats="title_text" class="post_region_title">lab01 a54</h1>

<div class="post_region_text" id="questionText"><p>Lab 01</p>
<h2>Due Tomorrow by 11:59 pm</h2>
<p dir="auto">Welcome!</p>
<p dir="auto">You are working in a Linux lab; the operating system on these computers is the Ubuntu variant of Linux. Enter your Binghamton user ID and PODS password to log on - if you are unable to log on, consult the TA. All your files are stored on your H drive which you can access outside the lab. Instructions on this can be found&nbsp;<a href="http://cs.binghamton.edu/%7Emhems1/cs140s17/remote_access.html" target="_blank" rel="noreferrer">here</a>. This&nbsp;<a href="http://cs.binghamton.edu/%7Emhems1/cs140s17" target="_blank" rel="noreferrer">website</a>&nbsp;also has some materials you may find helpful over the course of the semester.</p>
<h1>Some setup</h1>
<p dir="auto">For the beginning part of the course, we will be working from the terminal and coding in a simple text editor. Open up a terminal by clicking the black prompt icon in the bottom icon bar. Type&nbsp;<code>rm -rf .cache</code>&nbsp;and press the&nbsp;<strong>Enter</strong>&nbsp;key. This executes the&nbsp;<code>rm</code>&nbsp;command to remove the directory named .cache. Removing this directory is done to provide more memory space on your account. Next run the command&nbsp;<code>mkdir -p cs140/labs</code>&nbsp;which creates a&nbsp;<em>labs</em>&nbsp;directory within a&nbsp;<em>cs140</em>&nbsp;directory. Next change to the&nbsp;<em>labs</em>&nbsp;directory with the command&nbsp;<code>cd cs140/labs</code>. Notice your prompt has changed to reflect the directory change. More about the shell can be found&nbsp;<a href="http://cs.binghamton.edu/%7Emhems1/cs140s17/pitfalls/shell.html" target="_blank" rel="noreferrer">here</a>.</p>
<h1>Onto the lab</h1>
<h1>Baby Steps</h1>
<p dir="auto">Make a&nbsp;<em>lab01</em>&nbsp;directory with&nbsp;<code>mkdir lab01</code>&nbsp;and then run&nbsp;<code>cd lab01</code>&nbsp;to change directories to the lab01 directory. Whenever you want to create a new file or open an existing one, you&nbsp;<strong>would</strong>&nbsp;open the text editor with the name of the file like so:</p>
<p dir="auto"><code>gedit filename.java &amp;</code>.</p>
<p dir="auto">Create a file named&nbsp;<em>Hello.java</em>&nbsp;which will print out the text&nbsp;<code>"Hello, World!"</code>&nbsp;to the terminal. Copy/paste the following into&nbsp;<em>Hello.java</em>:</p>
<pre style="white-space: -moz-pre-wrap;white-space: -o-pre-wrap;white-space: pre-wrap;word-wrap: break-word;" class="prettyprint"><span class="kwd">package</span><span class="pln"> lab01</span><span class="pun">;</span><span class="pln"> </span><span class="com">// bundled in package based on name of assignment/lab</span><span class="pln">

</span><span class="com">// class name must match file name</span><span class="pln">
</span><span class="kwd">public</span><span class="pln"> </span><span class="kwd">class</span><span class="pln"> </span><span class="typ">Hello</span><span class="pln"> </span><span class="pun">{</span><span class="pln">
    </span><span class="com">// main method called implicity when you run program</span><span class="pln">
    </span><span class="kwd">public</span><span class="pln"> </span><span class="kwd">static</span><span class="pln"> </span><span class="kwd">void</span><span class="pln"> main</span><span class="pun">(</span><span class="typ">String</span><span class="pun">[]</span><span class="pln"> args</span><span class="pun">)</span><span class="pln"> </span><span class="pun">{</span><span class="pln">
        </span><span class="typ">System</span><span class="pun">.</span><span class="kwd">out</span><span class="pun">.</span><span class="pln">println</span><span class="pun">(</span><span class="str">"Hello, World!"</span><span class="pun">);</span><span class="pln"> </span><span class="com">// print out text</span><span class="pln">
    </span><span class="pun">}</span><span class="pln">
</span><span class="pun">}</span></pre>
<p dir="auto">With this minimal but complete program, we now must compile and run it. You'll need to learn the two commands to compile and run Java programs. To compile, run&nbsp;<code>javac -d . *.java</code>. To run, execute&nbsp;<code>java -cp . lab01.Hello</code>. You should see the text "Hello, World!" in the console. A more detailed explanation of what you have just done can be found&nbsp;<a href="http://cs.binghamton.edu/%7Emhems1/cs140s17/pitfalls/hello.html" target="_blank" rel="noreferrer">here</a>.</p>
<h1>Some Classes</h1>
<p dir="auto">The basic building block of Java programs is classes. Classes model real-world objects where the class's variables model an object's data and the class's methods model actions available on that object.</p>
<p dir="auto">Create a new file named&nbsp;<em>Loan.java</em>&nbsp;which will hold the code for a Loan class. Copy/paste the contents into that file:</p>
<pre style="white-space: -moz-pre-wrap;white-space: -o-pre-wrap;white-space: pre-wrap;word-wrap: break-word;" class="prettyprint"><span class="kwd">package</span><span class="pln"> lab01</span><span class="pun">;</span><span class="pln">

</span><span class="com">/**
 * A class representing a loan
 */</span><span class="pln">
</span><span class="kwd">public</span><span class="pln"> </span><span class="kwd">class</span><span class="pln"> </span><span class="typ">Loan</span><span class="pln"> </span><span class="pun">{</span><span class="pln">
    </span><span class="kwd">private</span><span class="pln"> </span><span class="kwd">double</span><span class="pln"> amount</span><span class="pun">;</span><span class="pln"> </span><span class="com">// amount the loan is for</span><span class="pln">
    </span><span class="kwd">private</span><span class="pln"> </span><span class="kwd">double</span><span class="pln"> interestRate</span><span class="pun">;</span><span class="pln"> </span><span class="com">// rate the loan takes on interest</span><span class="pln">

    </span><span class="com">/**
     * Construct a loan object given a loan amount
     * and an interest rate
     *
     * @param amt the amount of the loan
     * @param ir the interest rate
     */</span><span class="pln">
    </span><span class="kwd">public</span><span class="pln"> </span><span class="typ">Loan</span><span class="pun">(</span><span class="kwd">double</span><span class="pln"> amt</span><span class="pun">,</span><span class="pln"> </span><span class="kwd">double</span><span class="pln"> ir</span><span class="pun">)</span><span class="pln"> </span><span class="pun">{</span><span class="pln">
        </span><span class="kwd">this</span><span class="pun">.</span><span class="pln">amount </span><span class="pun">=</span><span class="pln"> amt</span><span class="pun">;</span><span class="pln">
        </span><span class="kwd">this</span><span class="pun">.</span><span class="pln">interestRate </span><span class="pun">=</span><span class="pln"> ir</span><span class="pun">;</span><span class="pln">
    </span><span class="pun">}</span><span class="pln">

    </span><span class="com">/**
     * Gets the amount the loan is for
     *
     * @return the amount of the loan
     */</span><span class="pln">
    </span><span class="kwd">public</span><span class="pln"> </span><span class="kwd">double</span><span class="pln"> getAmount</span><span class="pun">()</span><span class="pln"> </span><span class="pun">{</span><span class="pln">
        </span><span class="kwd">return</span><span class="pln"> amount</span><span class="pun">;</span><span class="pln">
    </span><span class="pun">}</span><span class="pln">

    </span><span class="com">/**
     * Gets the interest rate of the loan
     *
     * @return the interest rate of the loan
     */</span><span class="pln">
    </span><span class="kwd">public</span><span class="pln"> </span><span class="kwd">double</span><span class="pln"> getInterestRate</span><span class="pun">()</span><span class="pln"> </span><span class="pun">{</span><span class="pln">
        </span><span class="kwd">return</span><span class="pln"> interestRate</span><span class="pun">;</span><span class="pln">
    </span><span class="pun">}</span><span class="pln">

    </span><span class="com">/**
     * Return the amount to be paid back on the loan,
     * given a number of years that have passed
     *
     * @param years the amount of years that have passed
     * @return the amount due on the loan after `years` years have passed
     */</span><span class="pln">
    </span><span class="kwd">public</span><span class="pln"> </span><span class="kwd">double</span><span class="pln"> getAmountDue</span><span class="pun">(</span><span class="kwd">int</span><span class="pln"> years</span><span class="pun">)</span><span class="pln"> </span><span class="pun">{</span><span class="pln">
        </span><span class="kwd">double</span><span class="pln"> amt </span><span class="pun">=</span><span class="pln"> amount</span><span class="pun">;</span><span class="pln">
        </span><span class="kwd">for</span><span class="pln"> </span><span class="pun">(</span><span class="kwd">int</span><span class="pln"> i </span><span class="pun">=</span><span class="pln"> </span><span class="lit">0</span><span class="pun">;</span><span class="pln"> i </span><span class="pun">&lt;</span><span class="pln"> years</span><span class="pun">;</span><span class="pln"> i</span><span class="pun">++)</span><span class="pln"> </span><span class="pun">{</span><span class="pln">
            amt </span><span class="pun">+=</span><span class="pln"> amt </span><span class="pun">*</span><span class="pln"> interestRate</span><span class="pun">;</span><span class="pln">
        </span><span class="pun">}</span><span class="pln">
        </span><span class="kwd">return</span><span class="pln"> amt</span><span class="pun">;</span><span class="pln">
    </span><span class="pun">}</span><span class="pln">
</span><span class="pun">}</span></pre>
<p dir="auto">Look over the class you have just copied, noting the variables and methods contained in the class. Use the comments to assist your understanding.</p>
<p dir="auto">We can accomplish more when objects interact. Lets create a Loanee class that will model a person taking out a Loan.</p>
<p dir="auto">Copy/paste the following into a file named&nbsp;<em>Loanee.java</em>. Remember the filename tells you what the name of the class&nbsp;<strong>has</strong>&nbsp;to be and vice-versa.</p>
<pre style="white-space: -moz-pre-wrap;white-space: -o-pre-wrap;white-space: pre-wrap;word-wrap: break-word;" class="prettyprint"><span class="kwd">package</span><span class="pln"> lab01</span><span class="pun">;</span><span class="pln">

</span><span class="com">/**
 * A class representing a person taking out a loan
 */</span><span class="pln">
</span><span class="kwd">public</span><span class="pln"> </span><span class="kwd">class</span><span class="pln"> </span><span class="typ">Loanee</span><span class="pln"> </span><span class="pun">{</span><span class="pln">
    </span><span class="kwd">private</span><span class="pln"> </span><span class="kwd">int</span><span class="pln"> money</span><span class="pun">;</span><span class="pln">

    </span><span class="com">/**
     * Construct a loanee object given an amount of money (in dollars)
     * @param money the amount of dollars the person has
     */</span><span class="pln">
    </span><span class="kwd">public</span><span class="pln"> </span><span class="typ">Loanee</span><span class="pun">(</span><span class="kwd">int</span><span class="pln"> money</span><span class="pun">)</span><span class="pln"> </span><span class="pun">{</span><span class="pln">
        </span><span class="kwd">this</span><span class="pun">.</span><span class="pln">money </span><span class="pun">=</span><span class="pln"> money</span><span class="pun">;</span><span class="pln">
    </span><span class="pun">}</span><span class="pln">

    </span><span class="com">/**
     * Gets the money the Loanee has
     * @return the money the Loanee has
     */</span><span class="pln">
    </span><span class="com">// TODO fill in the blanks, use the Loan class as a guide</span><span class="pln">
    </span><span class="kwd">public</span><span class="pln"> _</span><span class="pun">?</span><span class="pln">_ getMoney</span><span class="pun">()</span><span class="pln"> </span><span class="pun">{</span><span class="pln">
        </span><span class="kwd">return</span><span class="pln"> _</span><span class="pun">?</span><span class="pln">_</span><span class="pun">;</span><span class="pln">
    </span><span class="pun">}</span><span class="pln">

    </span><span class="com">/**
     * Determines if this person could pay back a potential loan
     * given back an amount, an interest rate, and how many years
     * it will take for them to pay it all back at once
     *
     * @param amt the amount the loan is for
     * @param ir the interest rate of the loan
     * @param years the number of years to go by before they can
     * pay the loan
     * @return true if the Loanee can pay back the loan, false if
     * they cannot
     */</span><span class="pln">
    </span><span class="kwd">public</span><span class="pln"> </span><span class="kwd">boolean</span><span class="pln"> canPayLoan</span><span class="pun">(</span><span class="kwd">double</span><span class="pln"> amt</span><span class="pun">,</span><span class="pln"> </span><span class="kwd">double</span><span class="pln"> ir</span><span class="pun">,</span><span class="pln"> </span><span class="kwd">int</span><span class="pln"> years</span><span class="pun">)</span><span class="pln"> </span><span class="pun">{</span><span class="pln">
        </span><span class="com">// TODO</span><span class="pln">
        </span><span class="com">/*
         HINTS:
         Create a loan object with an amount and an interest rate
         Find the cost of that loan after a number of years
         Check if the person has enough money to pay back the loan
        */</span><span class="pln">
    </span><span class="pun">}</span><span class="pln">
</span><span class="pun">}</span></pre>
<p dir="auto">Read the provided code and then respond to the two TODOs that have to do with completing given methods. Read the comments to understand how the method should behave.</p>
<h1>Taking the code for a spin</h1>
<p dir="auto">We've written two classes so now we want to actually use those classes to accomplish some tasks. For now, we just want to do some simple tests of the&nbsp;<em>canPayLoan</em>&nbsp;method you've implemented.</p>
<p dir="auto">Copy/paste the following into&nbsp;<em>LoanSimulation.java</em>:</p>
<pre style="white-space: -moz-pre-wrap;white-space: -o-pre-wrap;white-space: pre-wrap;word-wrap: break-word;" class="prettyprint"><span class="kwd">package</span><span class="pln"> lab01</span><span class="pun">;</span><span class="pln">

</span><span class="com">/**
 * A simulation class that tests some loanees
 */</span><span class="pln">
</span><span class="kwd">public</span><span class="pln"> </span><span class="kwd">class</span><span class="pln"> </span><span class="typ">LoanSimulation</span><span class="pln"> </span><span class="pun">{</span><span class="pln">
    </span><span class="kwd">public</span><span class="pln"> </span><span class="kwd">static</span><span class="pln"> </span><span class="kwd">void</span><span class="pln"> main</span><span class="pun">(</span><span class="typ">String</span><span class="pun">[]</span><span class="pln"> args</span><span class="pun">)</span><span class="pln"> </span><span class="pun">{</span><span class="pln">
        </span><span class="com">// can $100 cover $100 over 10 years at 0%?</span><span class="pln">
        </span><span class="typ">Loanee</span><span class="pln"> person1 </span><span class="pun">=</span><span class="pln"> </span><span class="kwd">new</span><span class="pln"> </span><span class="typ">Loanee</span><span class="pun">(</span><span class="lit">100</span><span class="pun">);</span><span class="pln">
        </span><span class="kwd">boolean</span><span class="pln"> person1CanPay </span><span class="pun">=</span><span class="pln"> person1</span><span class="pun">.</span><span class="pln">canPayLoan</span><span class="pun">(</span><span class="lit">100</span><span class="pun">,</span><span class="pln"> </span><span class="lit">0</span><span class="pun">,</span><span class="pln"> </span><span class="lit">10</span><span class="pun">);</span><span class="pln">
        </span><span class="typ">System</span><span class="pun">.</span><span class="kwd">out</span><span class="pun">.</span><span class="pln">println</span><span class="pun">(</span><span class="pln">person1CanPay</span><span class="pun">);</span><span class="pln"> </span><span class="com">// should print true</span><span class="pln">

        </span><span class="com">// can $100 cover $100 over 1 year at 10%?</span><span class="pln">
        </span><span class="typ">Loanee</span><span class="pln"> person2 </span><span class="pun">=</span><span class="pln"> </span><span class="kwd">new</span><span class="pln"> </span><span class="typ">Loanee</span><span class="pun">(</span><span class="lit">100</span><span class="pun">);</span><span class="pln">
        </span><span class="kwd">boolean</span><span class="pln"> person2CanPay </span><span class="pun">=</span><span class="pln"> person2</span><span class="pun">.</span><span class="pln">canPayLoan</span><span class="pun">(</span><span class="lit">100</span><span class="pun">,</span><span class="pln"> </span><span class="lit">0.1</span><span class="pun">,</span><span class="pln"> </span><span class="lit">1</span><span class="pun">);</span><span class="pln">
        </span><span class="typ">System</span><span class="pun">.</span><span class="kwd">out</span><span class="pun">.</span><span class="pln">println</span><span class="pun">(</span><span class="pln">person2CanPay</span><span class="pun">);</span><span class="pln"> </span><span class="com">// should print false</span><span class="pln">

        </span><span class="com">// can $110 cover $100 over 1 year at 10%?</span><span class="pln">
        </span><span class="typ">Loanee</span><span class="pln"> person3 </span><span class="pun">=</span><span class="pln"> </span><span class="kwd">new</span><span class="pln"> </span><span class="typ">Loanee</span><span class="pun">(</span><span class="lit">110</span><span class="pun">);</span><span class="pln">
        </span><span class="kwd">boolean</span><span class="pln"> person3CanPay </span><span class="pun">=</span><span class="pln"> person3</span><span class="pun">.</span><span class="pln">canPayLoan</span><span class="pun">(</span><span class="lit">100</span><span class="pun">,</span><span class="pln"> </span><span class="lit">0.1</span><span class="pun">,</span><span class="pln"> </span><span class="lit">1</span><span class="pun">);</span><span class="pln">
        </span><span class="typ">System</span><span class="pun">.</span><span class="kwd">out</span><span class="pun">.</span><span class="pln">println</span><span class="pun">(</span><span class="pln">person3CanPay</span><span class="pun">);</span><span class="pln"> </span><span class="com">// should print true</span><span class="pln">
    </span><span class="pun">}</span><span class="pln">
</span><span class="pun">}</span></pre>
<p dir="auto">Now compile and run your code with the following two commands:</p>
<ul><li><code>javac -d . *.java</code></li><li><code>java -cp . lab01.LoanSimulation</code></li></ul>
<p dir="auto">Note the similarities between these commands and those you issued for&nbsp;<em>Hello.java</em>. More about this&nbsp;<a href="http://cs.binghamton.edu/%7Emhems1/cs140s17/pitfalls/compiling.html" target="_blank" rel="noreferrer">here</a>.</p>
<p dir="auto"></p>
<p dir="auto"><strong>Add the code lander provided before submission.</strong></p>
<h1>Submitting the lab to blackboard</h1>
<p dir="auto">To submit the lab to blackboard, you need to bundle the source code files into one compressed file and then upload that file to blackboard. First, change directory to the parent directory with&nbsp;<code>cd ..</code>. Next,&nbsp;<em>tar</em>&nbsp;the lab01 directory with the command</p>
<p dir="auto"><code>tar -czvf lab01.tar.gz lab01</code>.</p>
<p dir="auto">This will create a file&nbsp;<em>lab01.tar.gz</em>&nbsp;that holds the lab01 directory with your source code. Upload this file to the lab01 link in the Submissions folder in the A0 section of blackboard.</p><br></div>
<div data-pats="folders" class="post_region_folders">
  <span>
    <span data-pats="folders_item"><a data-pats="link" href="#" class="tag folder" onclick="PEM.fire('filterFeed', {filter:'folder',folder:'lab1'});return false;">lab1</a></span><span data-pats="folders_item"><a data-pats="link" href="#" class="tag folder" onclick="PEM.fire('filterFeed', {filter:'folder',folder:'a54'});return false;">a54</a></span>
  </span>
</div>
<div class="attachments" style="display:none;">
  <div class="attachments_divider"></div>
  <div class="attachments_count">Attachments:</div>
  <table class="attachments_list">
    
  </table>
</div>
<div class="post_region_message_wrapper">
  <div id="endorse_text"></div>
  
  
  

      </div>
    </div>
