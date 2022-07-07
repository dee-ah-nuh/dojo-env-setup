# Installing Python Locally

Please visit https://coding-dojo-data-science.github.io/dojo-env-setup-instructions/ for the complete installation instructions below as a multi-page website.
  
___
<!-- 
## Updating to New dojo-env


*   If you have already installed your dojo-env and wish to update to the new version, you must first remove the current dojo-env from your computer.
    *   **Note: the new version of dojo-env was released in July 2022.** If you installed your environment in July or later you already have the updated dojo-env.
*   **The benefits of upgrading to the new dojo-env:**
    *   New sklearn v1.1 with simplified column transformer feature names!
    *   Jupyter Lab added

*   New Packages and Tools Included:

*   nbdime: Version control for jupyter notebooks. 
*   Model Explainer Packages (SHAP, Lime, Yellowbrick)
*   Stack 2 & 3 Packages Previously Not Included:
    *   Tensorflow
    *   xgboost
    *   lightbgm
*   Pandas Profiling (incredibly powerful all-in-one EDA report)
*   Time Series Modeling:
    *   pmdarima
    *   prohpet
    *   sktime (though still some issues to resolve)
*   And more!

#### IMPORTANT NOTE FOR MAC USERS WITH AN APPLE CHIP (M1, M1Pro, M2, etc)!

The original v1 of dojo-env did not fully support Apple processors, but the new dojo-env does. HOWEVER, in order to do so, **Mac users with an Apple chip need to UNINSTALL ANACONDA and switch to using Miniforge**.  

Please see Step 1 - MacOS (Apple Chip) for detailed instructions on how to uninstall anaconda and install miniforge.

### Step 1: Remove Your Old dojo-env
--------------------------------

*   1.  Open your terminal/GitBash
    2.  Deactivate`dojo-env`: 
        1.  Type `conda activate base` (or source activate base if you are on older versions of windows) 
            1.  Your terminal should now say `(base)` next to your prompt instead of `(dojo-env)`.
    3.  Remove the old `dojo-env` using the command:

conda remove --name dojo-env --all

            Enter `y` to approve the removal of the environment and hit enter.  

      4. Wait for the env to be removed.

                    This will delete all of the files associated with JUST our `dojo-env`. 

                    Anaconda & GitBash will still be installed.  We will just need to re-install our `dojo-env`

  

### Step 2: Clone (or update) the dojo-env-setup repo 


1.  Navigate to the dojo-env-setup repo: [https://github.com/coding-dojo-data-science/dojo-env-setup](https://github.com/coding-dojo-data-science/dojo-env-setup)
2.  **Clone the Repository to Your Computer:**
    1.  Click the green Code button and select  "Open in GitHub Desktop. "
    2.  If you still have your previously cloned copy, GitHub Desktop should show a # and down arrow on the top right corner where it should say "Fetch Origin".
        1.  Press the button to "Fetch Origin", which will download the updated environment files. 
        2.  You may need to press it again if it changes to "Pull Origin"
    3.  If you've updated the repo successfully there should be no remaining #'s or arrows on the top right corner.
        1.  If so, click on the Repository menu > Open in Terminal (or Open in GitBash).

  

### Step 3: (Re)Create Your dojo-env using the updated repo


1.  Run the same commands from the original step "2. Setting Up Your `dojo-env` Environment" (summarized below).
    1.  If you are unsure about which version of the summary instructions below to use, please go to the original Step 2 lesson for your specific OS and follow those steps again. 
2.  **"Step 2: Setting Up Your Dojo-Env" Summary:**
    1.  Depending on your OS and processor, you will use a different environment file in the conda env create command. 
        1.  In the table below find the environment yml file name that is correct for your computer/OS.

Note: Whenever the instructions below refer to your <ENV\_FILE> below, it means the filename from the following list (without < >).

**Computer/OS Type**

**Environment File Name**

Windows 

environment\_windows.yml

MacOS with an Intel Processor

environment\_mac\_intel.yml

MacOS with an Apple Chip (m1, m1pro, m2,etc)

environment\_mac\_mchip.yml

*   Make sure you are still using a terminal inside the folder for the dojo-env-setup (pwd)
*   Run the following command (replace <ENV\_FILE> with your filename from the table above)

conda env create -f <env\_file>

*   **Wait (patiently) for the dojo-env to be created.** 
    *   Note: the new environment includes many additional tools and can take anywhere from 3-20 minutes to finish downloading and installing the packages for the new environment.
*   Once its complete, run the following "conda activate dojo-env" command:

conda activate dojo-env

*   Note for windows users:
    *    if you see a message that says "your terminal is not set up for conda activate", change the command to "source activate"

source activate dojo-env

*   You should now see "(dojo-env)" next to your prompt in your terminal (may be above the prompt, on the left, or on the right depending on your OS)

*   After confirming you now see (dojo-env) displayed next to your prompt:
    *   Run the following command to make sure Jupyter Notebook/Lab knows your new environment.

python -m ipykernel install --user --name dojo-env --display-name "Python (dojo-env)"

## Testing Your New Environment


*   From the same terminal window, **start jupyter notebook** (run `jupyter notebook` in your terminal) 
*   **Open the test notebook for your OS (windows vs mac).**
    *    EnvironmentTester-Mac.ipynb  or EnvironmentTester-Windows.ipynb 
*   **Select the Kernel Menu > Restart and Run All.** 
    *   The notebook should run all the way to the end.
        *    If it doesn't, contact your instructor for assistance.

#### Bonus: Jupyter Lab


Your new dojo-env also includes jupyter lab. It is very similar to jupyter notebook, but has a more fleshed out user interface that is more similar to Colab than jupyter notebook.

To start jupyter lab run the following command:

jupyter lab

## Cheat Sheet/Summary Steps


1\. Clone repo or Fetch & Pull: [https://github.com/coding-dojo-data-science/dojo-env-setup  
](https://github.com/coding-dojo-data-science/dojo-env-setup)

2\. Open in Terminal/GitBash.

Execute the following commands:

#### 1. Deactivate dojo-env 
`conda activate base`
- Windows users may need to use "source activate base"
#### 2. Remove dojo-env
`conda remove --name dojo-env --all`
- press y to confirm
#### 3. Create new environment
- run ONE of the following (depending on you computer)
```
conda env create -f environment\_mac\_mchip.yml
conda env create -f environment\_mac\_intel.yml
conda env create -f environment\_windows.yml
```
#### Wait patiently, once completed, activate new env
`conda activate dojo-env`
- windows users may need "source activate dojo-env"
#### Add dojo-env kernel to jupyter 
` python -m ipykernel install --user --name dojo-env --display-name "Python (dojo-env)" `
#### Boot up jupyter notebook 
`jupyter notebook `
- OR If you previously follwed  "3. Setting dojo-env as your default"
`jnb`
## Read Final step below code cell

*   **Final step:** Open and run the appropriate environment testing notebook for your OS:
    *   "EnvironmentTester-mac.ipynb"
    *   "EnvironmentTester-windows.ipynb"
*   Notify a TA or instructor if the notebook does not successfully run ALL cells.

Enjoy your new dojo-env!
------------------------ -->
<!DOCTYPE html>
<html><body><h1>dojo-env-setup</h1><br><p><strong>If the images below are not visible:please open <a href='README_lessons.html' target='_blank' rel='noopener noreferrer'>this file</a> in your webbrowser.</p></strong><br><hr></hr><br><h1>Installation Overview</h1>
<p><br></p>
<p><strong>These steps should take&nbsp; ~30-90 minutes,</strong> depending on the speed of your machine and internet
	connection.&nbsp;<br></p>
<p>Over the next ~5 lessons, you will:<br></p>
<ol>
	<li>&nbsp;Install GitHub Desktop,</li>
	<li>&nbsp;Install Anaconda&nbsp;(Python).</li>
	<li>&nbsp;Create a special Python environment (dojo-env)</li>
	<li>Supercharge Jupyter Notebooks with Extensions</li>
	<li>&nbsp;Install Visual&nbsp;Studio&nbsp;Code.&nbsp;</li>
</ol>
<p><br></p>
<p>For several steps, there are multiple versions of the instructions, depending on what operating system you are using.
</p>
<p>&nbsp;(i.e. a Windows computer, vs a Mac with an Intel processor, vs a Mac with an Apple Chip (m1/m1pro/m2/etc).)</p>
<p><dfn>For steps, 1-3, please make sure you are on the correct instruction page for your OS.</dfn></p>
<p><dfn></dfn></p>
<p><br></p>
<p><strong>Regardless of OS, you will be using tools that serve the following purposes:<br></strong></p>
<ul>
	<li>Your "Terminal"/"Shell":&nbsp;<ul>
			<li>The primary application you will use to execute coding-related commands.</li>
		</ul>
	</li>
	<li>A Python&nbsp;Distribution:<ul>
			<li>The fundamental infrastructure for installing Python.</li>
		</ul>
	</li>
	<li>GitHub Desktop:<ul>
			<li>App for working with and managing git repositories.&nbsp;</li>
		</ul>
	</li>
	<li>Our custom Python Environment (dojo-env)<ul>
			<li>A bundle of packages required for stacks 1-5+</li>
		</ul>
	</li>
	<li>Jupyter Notebooks / Jupyter Lab&nbsp;<ul>
			<li>The primary editor we will use (instead of Colab).</li>
		</ul>
	</li>
	<li>Visual&nbsp;Studio&nbsp;Code<ul>
			<li>A special text editor designed for code.&nbsp;It has many extensions and languages available.&nbsp;</li>
			<li>We will use it to edit special files, but it can also run notebooks too!</li>
		</ul>
	</li>
</ul>
<p><dfn><br></dfn></p>
<p><strong><em>Scroll down to the bottom of this page for the recording of the Python&nbsp;Installation Lecture from
			04/14.</em></strong></p>
<br>
<p><br></p>
<h2>If you encounter an error during installation:&nbsp;</h2>
<ul>
	<li><strong>First, read a little further down in the instructions</strong> to make sure we do not already address
		the error message that you ran into.</li>
	<li><strong>Second, reach out on your Discord channel </strong>to the TAs and/or your instructor&nbsp;</li>
	<li><strong>Third, if you do not receive a response by the end of the day</strong> on Discord, please email
		jirving@codingdojo.com</li>
</ul>
<h2>Python&nbsp;Installation Video Recording</h2>
<!-- <iframe src="https://player.vimeo.com/video/701383672?h=1bc863cf8e" width="640" height="414" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen="" class="vimeo_responsive" style="width: 938px; height: 606.769px;" data-ready="true"></iframe> -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/videoseries?list=PLmeeqPbYmMC38Sp2d5nsfMeATQ24Q4-x4"
	title="YouTube video player" frameborder="0"
	allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
	allowfullscreen></iframe><br><hr></hr><br><h1>1. Downloading and Installing Required Apps</h1>
<blockquote>Before we install our python environment, we need to take care of a couple requirements.&nbsp;</blockquote>
<p><strong>In step 1, we will install:</strong></p>
<ul>
	<li>Your "Terminal"/"Shell":&nbsp;<ul>
			<li>The primary application you will use to execute coding-related commands.</li>
		</ul>
	</li>
	<li>A Python&nbsp;Distribution (Anaconda/miniforge):<ul>
			<li>The fundamental infrastructure that will allow us to install Python.</li>
		</ul>
	</li>
	<li>GitHub Desktop:<ul>
			<li>The way we will work with git repositories and the starting point for our local workflows.</li>
		</ul>
	</li>
</ul>
<p></p>
<h3></h3>
<h2>There are different instructions for step 1, depending on your operating system.</h2>
<h2><i>Please&nbsp;</i><i>make sure you are on the correct version of step 1&nbsp;</i><i>before following the
		instructions:</i></h2>
<ul>
	<li>Step 1 - Windows&nbsp;</li>
	<li>Step 1 - MacOS (Intel&nbsp;Processor)</li>
	<li>Step 1 - MacOS (Apple Chip)&nbsp;</li>
</ul>
<h3>Note for Mac users - if you don't know which type of Mac you have :</h3>
<div>
	<h3></h3>
	<h3>
		<ul>
			<li>Check the "About this Mac" screen for your computer.&nbsp;<ul>
					<li>Click on the Apple symbol on the top-left corner of your screen.</li>
					<li><strong>Click About This Mac.&nbsp;</strong></li>
					<li>A window with your computer's specs will appear like the one in the screenshot below<ul>
							<li><img src="https://s3.us-east-1.amazonaws.com/General_V88/boomyeah2015/codingdojo/curriculum/content/chapter/1656714456__About this Mac -Intel.png"
									width="475" height="268"
									style="background-color: initial; width: 475px; height: 268px;"></li>
							<li>If it has a "Processor" line that says "Intel" you should follow the instructions for
								MacOS (Intel&nbsp;Processor)</li>
							<li>If it has a "Chip" line that says "Apple" then follow the instructions for MacOS (Apple
								Chip)&nbsp;</li>
						</ul>
					</li>
				</ul>
			</li>
		</ul>
		<p><br></p>
		<p></p>
		<p><br></p>


	</h3>
</div><br><hr></hr><br><h1>Step 1 - MacOS (Apple Chip)</h1>
<h2>Preface: Good News and Bad News</h2>
<ul>
	<li>So...you got one of those shiny new(ish) Mac computers with Apple chip, eh?&nbsp;We've got some good news and
		bad news for you.&nbsp;<ul>
			<li>The good news:<ul>
					<li>&nbsp;Your python code will run blisteringly fast compared to a Mac with an Intel chip!&nbsp;
					</li>
					<li>Code that may take hours elsewhere will only take minutes for your computer.&nbsp;</li>
				</ul>
			</li>
		</ul>
		<ul>
			<li>The bad news:<ul>
					<li>Your instructions for Tool #3 below (the Python Distribution) are going to be very different
						than the other operating systems.&nbsp;</li>
					<li>Additionally, there are still packages that have not yet been updated to be compatible with your
						processor.&nbsp;<ul>
							<li>But don't worry: everything that is in the other OS's dojo-env is also in yours!
								<br>Just a heads up if you go to install a new package and run into issues.
							</li>
						</ul>
					</li>
				</ul>
			</li>
		</ul>
	</li>
</ul>
<p><br></p>
<h1>STEP # 1 INSTRUCTIONS:</h1>
<p>Note: steps for Tools # 1 and 2 are the same for Mac users with an Intel processor.&nbsp;</p>
<h2>Tool #1: A Linux-based bash shell/terminal:</h2>
<ul>
	<li>Linux users and MacOS users have this built-in to their OS.<ul>
			<li>On MacOS, the shell is called "Terminal" and can be found
				in&nbsp;<code>Applications&gt;Utilities</code>&nbsp;in Finder</li>
			<li>OR you can use spotlight search and search for "Terminal".</li>
		</ul>
	</li>
</ul>
<h3>Tool #2: GitHub&nbsp;Desktop</h3>
<ul>
	<li>Download the installer from this link:&nbsp;&nbsp;<a href="https://desktop.github.com/" target="_blank">GitHub
			Desktop</a></li>
	<li>Once installation is complete, open the application.<ul>
			<li>Log into the same GitHub account you have been using for your projects.</li>
		</ul>
	</li>
	<li>Once you have logged into the app,&nbsp; open the Options menu<ul>
			<li>&nbsp;Select&nbsp;<code>"GitHub Desktop"</code>&nbsp;on the menu bar (top of the screen) and then
				select&nbsp;<code>Preferences</code>.</li>
			<li>Select the "Integrations" tab.</li>
			<li>Make sure the Shell dropdown menu says GitBash<ul>
					<li>If not, select it from the dropdown menu.</li>
				</ul>
			</li>
			<li>Click Save.</li>
		</ul>
	</li>
</ul>
<p>----------------------------------------------------------------------------------------------------------------------------
</p>
<blockquote><strong>Note: Here is where the instructions for Apple Chips will significantly deviate from the
		others.<br></strong></blockquote>
<ul>
	<li>The <strong>primary difference</strong>&nbsp;is that in order for us to use Apple-Chip compatible versions of
		packages (like TensorFlow),&nbsp;<strong>we CAN NOT use the standard Anaconda distribution.&nbsp;</strong></li>
	<li>There is a l<strong>ightweight alternative to Anaconda, called miniforge</strong>, that will install much of the
		<strong>same foundations as Anaconda,</strong> but with&nbsp;access to alternative versions of
		packages&nbsp;that are optimized for Apple Chips.<ul>
			<li><strong>Note/Warning: you would still be&nbsp;<em>able</em></strong><strong>&nbsp;to install Anaconda if
					you tried, but</strong> your computer will <strong>never</strong> be able to run TensorFlow if you
				use Anaconda. So please, take our word for it that it is worth following our alternative
				instructions&nbsp;</li>
		</ul>
	</li>
	<li>The following instructions are based on <a
			href="https://caffeinedev.medium.com/how-to-install-tensorflow-on-m1-mac-8e9b91d93706" target="_blank">this
			blog post</a>, should you wish to review it in-depth.<span></span></li>
</ul>
<p><br></p>
<h2>Tool #3: Python&nbsp;Distribution - miniforge</h2>
<p>Tool # 3 will involve several steps with several verification steps along the way. Make sure to follow each Step and
	Verification step below to ensure you have a problem-free python installation.</p>
<h3>Step 1: Install XCode&nbsp;(a Mac-specific developer toolkit from Apple)</h3>
<ul>
	<li>Run the command below in your Terminal.<ul>
			<li>Note: this step may take several minutes&nbsp;</li>
			<li>You may be asked to enter your password to approve the installation.&nbsp;This is your normal user
				password to log into your computer.</li>
		</ul>
	</li>
	<pre data-language="ruby" class="rainbow">xcode-select --install</pre>
</ul>
<h3>Step 2: Install Homebrew&nbsp; ( a database of downloadable apps/tools for Mac)</h3>
<p>Visit&nbsp;<a href="https://brew.sh/" target="_blank">https://brew.sh/</a>&nbsp;for more information about Homebrew
</p>
<ul>
	<li>To Install homebrew, run the following command in your Terminal (and make sure to read the steps below):</li>
</ul>
<pre data-language="ruby"
	class="rainbow">/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"</pre>
<ul>
	<li><strong>You may be asked to enter your password in your terminal.</strong>&nbsp;<ul>
			<li>This is the same password you use to log into your mac.&nbsp;</li>
			<li>Enter your password when prompted and hit Enter.&nbsp;<ul>
					<li>NOTE: You will not be able to see what keys you have typed, so just trust that it is recognizing
						your keystrokes and hit enter. It will notify you if the password was incorrect.</li>
				</ul>
			</li>
		</ul>
	</li>
	<li><strong>The installation process will pause and ask you "Press RETURN to continue or any other key to
			abort".</strong>&nbsp;<ul>
			<li>When it does, press Return/Enter!</li>
		</ul>
	</li>
	<li><strong>Step 2B: CRITICAL NOTE</strong>
		<ul>
			<li>When homebrew has finished installing, it may display a message telling you to run 1 or 2 commands in
				your Terminal.&nbsp;<ul>
					<li><strong>It is very important that you run those commands</strong>, otherwise, your terminal will
						not know that homebrew has been installed.</li>
				</ul>
			</li>
		</ul>
	</li>
</ul>
<h3>Step 2&nbsp;Verification:</h3>
<p>Confirm that homebrew was successfully installed:</p>
<ul>
	<li><strong>&nbsp;Open a New Terminal Window (shortcut: Cmd+N or Cmd+T) and run the "brew" command</strong>.&nbsp;
		<ul>
			<li>If it lists available commands, great!<ul>
					<li>&nbsp; You're all set to move forward.</li>
				</ul>
			</li>
			<li><strong>If it says brew not found,&nbsp;</strong>
				<ul>
					<li>You may have missed the commands to paste at the end of the homebrew installation.</li>
					<li>Try installing homebrew again and make sure to pay attention to the final text that's displayed
						and follow any additional instructions it displays.</li>
				</ul>
			</li>
		</ul>
	</li>
</ul>
<h2>Step 3: Install miniforge using homebrew.</h2>
<h3>Pre-Step 3 Verification:</h3>
<ul>
	<li><strong>VERIFY THAT ANACONDA HAS NEVER BEEN PREVIOUSLY INSTALLED ON YOUR COMPUTER&nbsp;&nbsp;BY ANY
			USER.</strong>
		<ul>
			<li>Open a terminal window and run the "conda" command (without quotation marks).&nbsp;<ul>
					<li>If it says conda not found, great!&nbsp;<ul>
							<li>You're ready to install miniforge.&nbsp;</li>
						</ul>
					</li>
					<li>If it shows a list of available conda commands:<ul>
							<li><strong>You&nbsp;MUST FOLLOW THE APPENDIX INSTRUCTIONS AT THE BOTTOM FOR "Uninstalling
									Anaconda"</strong></li>
						</ul>
					</li>
				</ul>
			</li>
		</ul>
	</li>
</ul>
<p>
	<font color="#3e4e5a" face="Gotham-Rounded-Bold"><span></span></font>
</p>
<ul>
	<li><dfn><dfn></dfn></dfn><dfn>CRITICAL NOTE:&nbsp;</dfn>
		<ul>
			<li><dfn>IF YOUR TERMINAL RECOGNIZED THE CONDA COMMAND&nbsp;</dfn><b>ANACONDA MUST BE REMOVED BEFORE
					INSTALLING MINIFORGE.&nbsp;</b></li>
			<li>Failure to heed this warning will break all of your python environments and it is NOT easy to fix!!!
			</li>
		</ul>
	</li>
</ul>
<h3>Step 3 Commands:</h3>
<ul>
	<li>Enter the brew installation command below in your terminal:</li>
</ul>
<div>
	<pre data-language="ruby" class="rainbow">brew install miniforge</pre>
	<ul>
		<li>Once miniforge has finished installing, run the following command in your terminal (required for
			Matplotlib):</li>
	</ul>
	<pre data-language="ruby" class="rainbow">brew install pkg-config</pre>
	<h3>Post-Step 3 Verification</h3>
</div>
<ul>
	<li><strong>Open a new terminal window and enter the "conda" command.</strong>
		<ul>
			<li>If it lists available commands, fantastic!!&nbsp;<ul>
					<li><strong>You are all set to move on to the next page of instructions&nbsp;"2. Setting Up Your
							dojo-env Environment"!!</strong></li>
				</ul>
			</li>
			<li>If it says conda not found, try restarting your computer and then try running the conda command again.
				<ul>
					<li>If it still says conda not found, reach out to your instructor or a TA for help&nbsp;ASAP.</li>
				</ul>
			</li>
		</ul>
	</li>
</ul>
<p><br></p>
<p>-------------------------------------------------------------------------------------------------------------------
</p>
<h2>APPENDIX: UNINSTALLING ANACONDA</h2>
<p>If your computer already knew the conda command during "Pre-Step 3 Verification", it is critical that you remove
	anaconda before continuing with the miniforge installation.</p>
<p><strong>Pre-Uninstallation Verification Step:</strong></p>
<ul>
	<li><strong>If you share your computer with another User who also uses Python:</strong>
		<ul>
			<li>Pause here and check with them BEFORE you uninstall anaconda.&nbsp;&nbsp;<strong>You will be removing
					all of their python environments too,</strong> even though they have a separate User account.</li>
		</ul>
	</li>
</ul>
<ul>
	<li><strong>If you share your computer with someone and they have concerns about uninstalling
			anaconda:&nbsp;</strong>
		<ul>
			<li><strong>Stop here (for now)</strong>.<ul>
					<li>Do not move forward with the instructions until you have spoken with your instructor.&nbsp;</li>
					<li>Your instructor may be able to address concerns that your fellow User has and convince them to
						let you install miniforge.&nbsp;</li>
				</ul>
			</li>
		</ul>
	</li>
</ul>
<ul>
	<li><strong>Alternatively, you could follow the Step 1 - MacOS (Intel Processor) instructions instead but:</strong>
		<ul>
			<li>Your python code will run slower than it would with miniforge.</li>
			<li>You will not be able to import tensorflow without your kernel crashing.</li>
		</ul>
	</li>
</ul>
<ul>
	<li>Your instructor may be able to address concerns that your fellow User has and convince them to let you install
		miniforge.&nbsp;</li>
</ul>
<h4>Official&nbsp;Steps for Fully Uninstalling Anaconda:</h4>
<p>The following steps are taken directly from the <a href="https://docs.anaconda.com/anaconda/install/uninstall/"
		target="_blank">Official&nbsp;Uninstalling Anaconda documentation page</a>, specifically "Option B. Full
	uninstall using Anaconda-Clean and simple remove."</p>
<ul>
	<li><strong>Install the Anaconda-Clean package from Anaconda Prompt (terminal on Linux or macOS):</strong></li>
</ul>
<pre data-language="ruby" class="rainbow">conda install anaconda-clean</pre>
<ul>
	<li>In the same window, run the following command:</li>
</ul>
<pre data-language="ruby" class="rainbow">anaconda-clean --yes</pre>
<ul>
	<li>Once the process has been completed, manually delete any "anaconda3" or "anaconda2" folders that still
		exist.&nbsp;<ul>
			<li>It may be located in one of several&nbsp;possible folders. Run the following "ls -a" commands until you
				see a folder called "anconda2" or "anaconda3".&nbsp;</li>
			<li><strong>Once you see an anaconda folder, take note of:</strong>
				<ul>
					<li><strong>&nbsp;Which command showed the folder.</strong>
						<ul>
							<li><strong>&nbsp;Specifically, what did the command say after "ls -a"&nbsp;</strong></li>
							<li>We will refer to this as your "base folder" in the final step.</li>
						</ul>
					</li>
					<li><strong>If the anaconda folder was "anconda2" or "anaconda3"</strong>
						<ul>
							<li>We will refer to this as your "anaconda folder" in the final step.</li>
						</ul>
					</li>
				</ul>
			</li>
			<li><strong>and j</strong>ump to the very last command at the bottom of the page, with those 2 pieces of
				information.</li>
		</ul>
	</li>
</ul>
<pre data-language="ruby" class="rainbow">ls -a ~/
ls -a ~/opt/
ls -a /opt/</pre>
<ul>
	<li>Run the final command to remove the anaconda folder once you've identified your "base folder" and "anaconda
		folder".<ul>
			<li>Replace {base_folder} with the actual folder name</li>
		</ul>
		<ul>
			<li>Replace {anaconda_folder} with the actual folder name.</li>
		</ul>
	</li>
</ul>
<pre data-language="ruby" class="rainbow">rm -rf {base_folder}{anaconda_folder}
</pre>
<p><br></p>
<p>Once you've replaced the placeholder folder names with your actual folder names, the command should look something
	like this:</p>
<pre data-language="ruby" class="rainbow">rm -rf ~/opt/anaconda3
# or 
rm -rf ~/anaconda2
# or 
rm -rf ~/opt/anaconda3</pre>
<h4></h4>
<h4>Final Verification&nbsp;Step:</h4>
<ul>
	<li>Now, open a <strong>new</strong> terminal window and try running the "conda" command again. Your terminal should
		say that conda is not found.<ul>
			<li>If it says conda is not found, you are now ready to jump back up to the "Step 3 Commands" header above.
			</li>
		</ul>
		<ul>
			<li>If your computer still displays a list of conda commands, see the final portion of the <a
					href="https://docs.anaconda.com/anaconda/install/uninstall/#removing-anaconda-path-from-bash-profile"
					target="_blank">Official Uninstallation Instructions "Removing Anaconda from
					.bash_profile"</a>&nbsp; <strong>You may want to contact your instructor if you do not understand
					the final instructions in the official instructions.</strong></li>
		</ul>
	</li>
</ul><br><hr></hr><br><h1>Step 1 - MacOS (Intel Processor)</h1>
<p></p><b>
    <h3>Tool #1: A Linux-based bash shell/terminal:</h3>
    <ul>
        <li>Linux users and MacOS users have this built-in to their OS.<ul>
                <li>On MacOS, the shell is called "Terminal" and can be found
                    in&nbsp;<code>Applications&gt;Utilities</code>&nbsp;in Finder</li>
                <li>OR you can use spotlight search and search for "Terminal".</li>
            </ul>
        </li>
    </ul>
</b>
<h3>Tool #2: GitHub&nbsp;Desktop</h3>
<ul>
    <li>Download the installer from this link:&nbsp;&nbsp;<a href="https://desktop.github.com/" target="_blank">GitHub
            Desktop</a></li>
    <li>Once installation is complete, open the application.<ul>
            <li>Log into the same GitHub account you have been using for your projects.</li>
        </ul>
    </li>
    <li>Once you have logged into the app,&nbsp; open the Options menu<ul>
            <li>&nbsp;Select&nbsp;<code>"GitHub Desktop"</code>&nbsp;on the menu bar (top of the screen) and then
                select&nbsp;<code>Preferences</code>.</li>
            <li>Select the "Integrations" tab.</li>
            <li>Make sure the Shell dropdown menu says GitBash<ul>
                    <li>If not, select it from the dropdown menu.</li>
                </ul>
            </li>
            <li>Click Save.</li>
        </ul>
    </li>
</ul>
<h3>Tool #3: Python&nbsp;Distribution - Anaconda&nbsp;</h3>
<ul>
    <li>Anaconda is a data-science-focused python distributable that comes with a convenient GUI program for working
        with our python environments.&nbsp;</li>
    <li>Download and run the installer from the following link:&nbsp;<a
            href="https://www.anaconda.com/products/individual" target="_blank">Anaconda Individual Edition</a>
        <ul>
            <li>Use the default options,&nbsp;EXCEPT when you see the "Advanced Installation Options"&nbsp;window (like
                in the screenshot below).</li>
            <li>Select "Add Anaconda3 to my Path environment variable". Disregard the warning message will appear in red
                text.<ul>
                    <li>BOTH options should be checked, like in the screenshot below:</li>
                </ul>
            </li>
        </ul>
    </li>
</ul>
<figure><img
        src="https://s3.us-east-1.amazonaws.com/General_V88/boomyeah2015/codingdojo/curriculum/content/chapter/1647633851__anaconda_check_path.png"
        width="402" height="307" style="max-width: 100%; height: 307px; width: 402px;"></figure>
<p></p>
<blockquote><strong>You are all set to move on to the next lesson "2. Setting Up Your dojo-env Environment"</strong>
</blockquote>
<p><br></p>
<p><br></p><br><hr></hr><br><h1>Step 1 - Windows</h1>
<h3>Tool #1: A Linux-based bash shell/terminal:</h3>
<ul>
	<li><strong>Windows users should install GitBash</strong>, instead of using the windows command prompt<ul>
			<li>Otherwise, all of the commands for working with your terminal will not match the curriculum and other
				cloud-based platforms (like Amazon Web Services).<ul>
					<li>Note: for a list of the equivalent commands for Windows command prompt see <a
							href="https://www.geeksforgeeks.org/linux-vs-windows-commands/" target="_blank">this cheat
							sheet</a>.</li>
				</ul>
			</li>
			<li>Download the Git for Windows Installer:&nbsp;<a href="https://gitforwindows.org/">Git for Windows
					download</a>
				<ul>
					<li>Select the default options.</li>
				</ul>
			</li>
		</ul>
	</li>
</ul>
<h3>Tool #2: GitHub&nbsp;Desktop</h3>
<ul>
	<li>Download the installer from this link:&nbsp;&nbsp;<a href="https://desktop.github.com/" target="_blank">GitHub
			Desktop</a></li>
	<li>Once installation is complete, open the application.<ul>
			<li>Log into the same GitHub account you have been using for your projects.</li>
		</ul>
	</li>
	<li>Once you have logged into the app,&nbsp; open the Options menu<ul>
			<li>&nbsp;Click on&nbsp;<code>File</code>&nbsp;in the menu bar and then
				select&nbsp;<code>Options</code>&nbsp;</li>
			<li>Select the "Integrations" tab.</li>
			<li>Make sure the Shell dropdown menu says GitBash<ul>
					<li>If not, select it from the dropdown menu.</li>
				</ul>
			</li>
			<li>Click Save.</li>
		</ul>
	</li>
</ul>
<h3>Tool #3: Python&nbsp;Distribution - Anaconda&nbsp;</h3>
<ul>
	<li>Anaconda is a data-science-focused python distributable that comes with a convenient GUI program for working
		with our python environments.&nbsp;</li>
	<li>Download and run the installer from the following link: <a href="https://www.anaconda.com/products/individual"
			target="_blank">Anaconda Individual Edition</a>
		<ul>
			<li>Use the default options, <strong>EXCEPT when you see the "Advanced Installation Options"</strong> window
				(like in the screenshot below).</li>
			<li>Select "Add Anaconda3 to my Path environment variable". Disregard the warning message will appear in red
				text.<ul>
					<li>BOTH options should be checked, like in the screenshot below:</li>
				</ul>
			</li>
		</ul>
	</li>
</ul>
<figure><img
		src="https://s3.us-east-1.amazonaws.com/General_V88/boomyeah2015/codingdojo/curriculum/content/chapter/1647633851__anaconda_check_path.png"
		style="width: 402px; height: 307px;" width="402" height="307"></figure>
<h3>
	<font face="Gotham-Rounded-Medium">
		<div>
			<h3>
				<font face="Gotham-Rounded-Medium"><br></font>
			</h3>
		</div>Tool #3 -&nbsp;Verification: Making sure GitBash Knows "conda"
	</font>
</h3>
<ol>
	<li>
		<p>Windows users may need to take an additional step to get anaconda and GitBash working together.</p>
	</li>
	<li>
		<p>Open GitBash from your start menu.&nbsp;</p>
	</li>
	<li>
		<p>Enter the command&nbsp;<code>conda</code> and press enter.</p>
		<ol>
			<li><strong>If you see a list of available conda commands, great!&nbsp;</strong>
				<ol>
					<li>You are all set to move on to Step 2: "Setting Up Your <code>dojo-env</code>"</li>
					<li>Disregard the final section below that says "Adding Conda to&nbsp;GitBash"</li>
				</ol>
			</li>
			<li><strong>If you see a message that says: "bash: conda: command not found", then follow the instructions
					below under "Adding Conda to&nbsp;GitBash"</strong></li>
		</ol>
	</li>
</ol>
<h3>Adding Conda to GitBash:</h3>
<p>Note: the instructions below are adapted from this <a
		href="https://fmorenovr.medium.com/how-to-add-conda-to-git-bash-windows-21f5e5987f3d">Blog Post</a></p>
<ul>
	<li>Once you have installed anaconda, use File Explorer to Open Your <strong>User</strong> folder. (Windows key +E
		is shortcut for File Explorer)<ul>
			<li>This is the folder that contains your Desktop, Downloads, My Documents, and other user-specific files.
				<ul>
					<li>Example: <code>Users/your_name/<br></code></li>
				</ul>
			</li>
			<li>If you're having trouble finding your user folder:<ul>
					<li>Go to This PC in File Explorer, and then double click on your C drive.<ul>
							<li>Then double click the Users folder and then click on the folder that corresponds to your
								windows username.</li>
						</ul>
					</li>
				</ul>
			</li>
		</ul>
	</li>
	<li>Inside your user folder, you should see a folder named "<code>anaconda3</code>" (note: not the hidden folder
		called <code>.anaconda</code> that starts with a <code>.</code>). Double-click the folder to open it.<ul>
			<li>Yous should see a folder named&nbsp;<code>etc</code>&nbsp;inside the <code>anaconda3</code> folder. Open
				it.</li>
			<li>You should see a folder called&nbsp;<code>profile.d</code> folder inside the <code>etc</code>. Open it.
				<ul>
					<li>You should see a <code>conda.sh</code> file in this folder&nbsp;<ul>
							<li>(Note: depending on your setting in File Explorer, it may not show the .sh and may just
								show "conda".&nbsp;</li>
						</ul>
					</li>
				</ul>
			</li>
		</ul>
		<ul>
			<li>Right-click somewhere in the "profile.d" folder and select "Git Bash Here".</li>
		</ul>
	</li>
	<li>&nbsp;From the GitBash window that opens:<ul>
			<li>Enter the command <code>pwd</code>&nbsp;and hit enter and examine the file path that's displayed<ul>
					<li>If the file path displayed ends with <code>profile.d</code> then are in the right folder!</li>
					<li>If not, restart the "Adding Conda to&nbsp;GitBash" instructions again and make sure you can find
						your profile.d folder.&nbsp;<ul>
							<li>Reach out to your instructor or a TA if you are still having issues.</li>
						</ul>
					</li>
				</ul>
			</li>
			<li class="text-justify">Next, Enter the following command and hit enter:<ul>
					<li><code>echo ". '${PWD}'/conda.sh" &gt;&gt; ~/.bashrc<br></code></li>
				</ul>
			</li>
		</ul>
	</li>
	<li>Open a new GitBash window and enter <code>conda</code> again.&nbsp;<ul>
			<li>You should no longer get the "bash: conda: command not found" error message!<ul>
					<li>Reach out to your instructor or a TA if you are still having issues.</li>
				</ul>
			</li>
		</ul>
	</li>
</ul>
<p><br></p>
<p><br></p>
<blockquote><strong>You are all set to move on to the next lesson "2. Setting Up Your dojo-env Environment"</strong>
</blockquote>
<p> <br> <br> <br></p>
<p> <br> <br></p><br><hr></hr><br><h1>Step 2.1 Clone the dojo-env-setup repository</h1>
<ol>
	<li><strong>Open the dojo-env-setup repository&nbsp;on&nbsp;GitHub.com:</strong>
		<ol>
			<li>&nbsp;<a
					href="https://github.com/coding-dojo-data-science/dojo-env-setup">https://github.com/coding-dojo-data-science/dojo-env-setup</a>
			</li>
		</ol>
	</li>
	<li><strong>Make sure that :</strong>
		<ol>
			<li>you are <strong>logged in to your account on&nbsp;GitHub.com&nbsp;</strong></li>
			<li>and you are logged into<strong> the SAME account in the GitHub Desktop </strong>app (that you installed
				in step 1.)</li>
		</ol>
	</li>
	<li class="text-center"><strong>Click on the green <code>Code</code> button and then click
			<code>Open in GitHub desktop.<br></code></strong><img
			src="https://s3.us-east-1.amazonaws.com/General_V88/boomyeah2015/codingdojo/curriculum/content/chapter/1656802816__clone_repo.png"
			width="608" height="307" style="width: 608px; height: 307px;">
		<p><br></p>
		<p><br></p>
		<ol>
			<li class="text-center"><strong>GitHub desktop should open automatically&nbsp;</strong>and ask you what
				folder you would like to store your repository in.<p><br></p>
				<figure><img
						src="https://s3.us-east-1.amazonaws.com/General_V88/boomyeah2015/codingdojo/curriculum/content/chapter/1656806399__clone-repo-menu.png"
						style="width: 339px; height: 207px;" width="339" height="207"></figure>
				<p><br></p>
				<ol>
					<li><strong>Troubleshooting Note:&nbsp;if you are brought to the Download GitHub Desktop web page
							instead:</strong>
						<ol>
							<li>&nbsp;It means you were not logged into the same account on GitHub.com and
								GitHub&nbsp;Desktop when you clicked Open in&nbsp;GitHub Desktop.&nbsp;<ol>
									<li>Make sure you see your user profile pic in the top right of GitHub.com&nbsp;
									</li>
									<li>and check your&nbsp;Account in GitHub&nbsp;Desktop's Preferences/Options menu.
									</li>
									<li>and then try again.</li>
								</ol>
							</li>
						</ol>
					</li>
				</ol>
			</li>
		</ol>
		<ol>
			<li class="text-center">By default, GitHub Desktop <strong>will use a new "GitHub" folder in your Documents
					folder</strong>
				<ol>
					<li class="text-center">GitHub Desktop will create a NEW folder with the same name as the repository
						INSIDE of whichever folder you select.</li>
					<li><strong>If you use the default options, then this will&nbsp;create a "dojo-env-setup/" folder
							inside of "Documents/GitHub/"</strong></li>
					<li><strong>Note: it is strongly recommended that you use the Documents/GitHub folder for this
							repository.</strong>
						<p><br></p>
						<ol>
							<li>But if you'd rather save the folder somewhere else:<ol>
									<li>Use the "Choose" button (the button name may be&nbsp; "Browse"&nbsp;on Windows).
									</li>
									<li>A window should pop up for you to find and click on the folder where you want to
										create the "dojo-env-setup" folder.</li>
									<li>Once you have selected a new folder using the Browse button, you should see the
										full folder path displayed.</li>
									<li><strong>IMPORTANT STEP: Make sure to remember the full file path of the folder
											you selected! </strong>(See the screenshot below.&nbsp;)<ol>
											<li>
												<figure><img
														src="https://s3.us-east-1.amazonaws.com/General_V88/boomyeah2015/codingdojo/curriculum/content/chapter/1656806548__clone-repo-menu annotated.png"
														style="width: 356px; height: 217px;" width="356" height="217">
												</figure>
											</li>
										</ol>
									</li>
								</ol>
							</li>
						</ol>
					</li>
				</ol>
			</li>
		</ol>
	</li>
</ol>
<p>
	<font color="#505050" face="Gotham-Rounded-Medium"><br></font>
</p><br><hr></hr><br><h1>Step 2.2: Open the Repo in Terminal/GitBash</h1>
<h2>Step 2.2: Open the Repo in Terminal (mac) or GitBash&nbsp;(windows)</h2>
<p>Once you have cloned the repository, you will need to open a terminal/gitbash window in the same folder as the
	repository.</p>
<ul>
	<li><strong>Open a new terminal in the dojo-env-setup folder</strong>
		<ul>
			<li>First, in GitHub Desktop: make sure the left sidebar says "dojo-env-setup" in the top-left corner under
				Current Repository.</li>
		</ul>
		<ul>
			<li><strong>Click on the Repository menu and select "<code>Open in terminal</code>" or
					"<code>Open in gitbash</code>"</strong>
				<ul>
					<li>Windows Users: the menu will be at the top of GitHub&nbsp;Desktop's window.</li>
					<li>Mac Users: the menu will appear at the very top of your screen (your menu bar).</li>
				</ul>
			</li>
			<li><strong>Alternatively, you can use the keyboard shortcut to do the same thing. The command for both Mac
					and Windows is:</strong>
				<ul>
					<li><strong>Control + `</strong>&nbsp; (the key above tab that also has the tilde symbol ~)</li>
				</ul>
			</li>
		</ul>
	</li>
	<li><strong>In the terminal window that appears,&nbsp;type the "pwd" command (stands for print working directory)
			and press Enter.</strong>
		<ul>
			<li>It will display the folder name of the folder your terminal is currently located.&nbsp;<ul>
					<li>The folder path should end in "dojo-env-setup/"</li>
					<li>If you used the default GitHub folder when you cloned dojo-env, the full filepath would be
						something similar to "/Users/yourname/Documents/GitHub/dojo-env-setup/"</li>
				</ul>
			</li>
		</ul>
	</li>
</ul>
<p><br></p>
<h3>Troubleshooting (Windows):&nbsp;</h3>
<div>
	<p>If you are having trouble getting GitHub desktop to open&nbsp;GitBash in the correct folder there are 2 solutions
		for getting your gitbash window in the dojo-env-setup folder.</p>
	<ul>
		<li>
			<font color="#505050" face="Gotham-Rounded-Medium"><strong>Solution #1: Using File Explorer +
					Right&nbsp;Click</strong></font>
			<ul>
				<li>If you followed the instructions in step 1 and used the default options when install Git for
					Windows/GitBash, you should have a new option in your Right-Click menu that says "GitBash here".
				</li>
			</ul>
			<ul>
				<li>In&nbsp;GitHub Desktop <strong>click the Repository menu again and select "Show in File
						Explorer".</strong></li>
				<li>Once file explorer opens,<strong> right-click anywhere inside the folder </strong>(right-click on
					empty space, not on a file)&nbsp;<strong>and select GitBash here</strong>.<ul>
						<li>A GitBash window should open in the correct folder.</li>
					</ul>
				</li>
			</ul>
		</li>
		<li>Type pwd to confirm that you are indeed in the dojo-env-setup folder.</li>
	</ul>
	<p>
	</p>
	<ul>
		<li><strong>Solution #2:&nbsp;Open a new GitBash and navigate to the right folder.</strong>
			<ul>
				<li>If you do not have the option to "GitBash here", you can manually navigate there in GitBash.</li>
				<li><strong>Open the windows start menu, find and click on GitBash to open a new window.<br></strong>
				</li>
				<li><strong>Important Note: You must know the full file path for the repo for the next step. We will
						refer to as &lt;repo_filepath&gt; in the instructions below.</strong>
					<ul>
						<li><strong>&nbsp;if you used the suggested default folder </strong>when cloning the repo, your
							repo_filepath should be:&nbsp;<ul>
								<li>" /Users/&lt;your name&gt;/Documents/GitHub/dojo-env-setup"&nbsp;&nbsp;<ul>
										<li>But instead of&nbsp; &lt;your name&gt; it will be your actual user name for
											your computer</li>
									</ul>
									<ul>
										<li>If you are not sure what your username is, run the "whoami" command in your
											GitBash to see your user name.</li>
									</ul>
								</li>
							</ul>
						</li>
						<li><strong>If you did NOT use the suggested default folder,&nbsp;</strong>
							<ul>
								<li>Your repo_filepath will be the path displayed in the window that appeared when you
									cloned the repo.<ul>
										<li>You should have taken note of the file path you selected, as indicated in
											the screenshot.</li>
									</ul>
								</li>
							</ul>
						</li>
					</ul>
				</li>
			</ul>
			<ul>
				<li>Once you know what your repo_filepath is navigate to that folder using the&nbsp;change directory
					command (cd)<ul>
						<li>"cd&nbsp; &lt;repo_filepath&gt;".</li>
						<li>See the examples below:</li>
					</ul>
				</li>
			</ul>
		</li>
	</ul>
	<pre class="rainbow" data-language="ruby">## Examples are assuming your username is "codingdojo"
						# Example if you used default folder:
						cd /Users/codingdojo/Documents/GitHub/dojo-env-setup/
						# Example if you used a different folder. e.g. you made a Boot&nbsp;Camp&nbsp;Stuff folder in your Documents folder.
						cd /Users/codingdojo/Documents/Boot Camp&nbsp;Stuff/</pre>
	<p><br></p>
	<h3></h3>
	<h2>Verify Step 2.2</h2>
	<p>Run one last command to verify that you are indeed in the correct folder.&nbsp;</p>
	<p>Run the "ls -a" command to see a detailed list of all files in the repo.</p>
	<pre>ls -a</pre>
	<p>You should see a list of all the files in the current folder.&nbsp;</p>
	<p><br></p>
	<p><strong>If you are in the right folder, you should see 3 files that start with "environment" and end with ".yml"
			like in the screenshot below.</strong></p>
	<figure><img
			src="https://s3.us-east-1.amazonaws.com/General_V88/boomyeah2015/codingdojo/curriculum/content/chapter/1656808093__dojo-env-setup ls result.png"
			style="width: 493px; height: 195px;" width="493" height="195"></figure>
	<p><strong>If so, you are all set for the next step: create the dojo-env environment!</strong></p>
	<p><br></p>
	<p><br></p>


</div><br><hr></hr><br><h1>Step 2.3 Create the dojo-env environment</h1>
<h3>
	Identify the correct environment file for your computer</h3>
<ul>
	<li>Depending on your OS and processor, you will use a different environment file name in your "conda create"
		command.</li>
	<li><strong>In the table below find the environment yml file name that is correct for your computer/OS.</strong>
		<ul>
			<li>Reminder for Mac Users: see Lesson 1. Downloading and Installing Required Apps to remember how to
				identity if you have an Intel processor or an Apply chip.</li>
		</ul>
	</li>
</ul>
<pre class="rainbow" data-language="ruby">## General Format of the command to create env (but replace &lt;env_file&gt; with filename from table below
			conda env create -f &lt;env_file&gt;
			</pre>
<table>
	<tbody>
		<tr>
			<td><strong>Computer/OS Type</strong></td>
			<td><strong>Environment File&nbsp;Name</strong></td>
		</tr>
		<tr>
			<td>Windows&nbsp;</td>
			<td>environment_windows.yml</td>
		</tr>
		<tr>
			<td>MacOS with an Intel&nbsp;Processor</td>
			<td>environment_mac_intel.yml</td>
		</tr>
		<tr>
			<td>MacOS with an Apple Chip (m1, m1pro, m2,etc)</td>
			<td>environment_mac_mchip.yml</td>
		</tr>
	</tbody>
</table>
<h3>Create the dojo-env using "conda create"</h3>
<ul>
	<li><strong>After you've identified the right environment for your computer, run the "conda env create -f
			&lt;env_file&gt;".&nbsp;</strong></li>
</ul>
<pre data-language="ruby" class="rainbow">## Env Creation Commands by OS
			# Windows 
			conda env create -f environment_windows.yml
			# Mac -&nbsp;Intel Processor 
			conda env create -f environment_mac_intel.yml
			# Mac - Apple Chip 
			conda env create -f environment_mac_intel.yml
			</pre>
<ul>
	<li><strong>Wait (patiently) for the dojo-env to be created.&nbsp;</strong>
		<ul>
			<li>
				<font color="#505050">It</font> can take anywhere from 3-20 minutes to finish create the environment,
				depending on your computer and internet connection.
			</li>
			<li>You will see several progress bars during the process. Once it has been completed you should see a
				message that says</li>
		</ul>
	</li>
</ul>
<pre class="rainbow" data-language="ruby"># To activate this environment use:
			&nbsp; &nbsp; $ conda activate dojo-env
			# To deactivate this environment use:
			&nbsp; &nbsp; $ conda deactivate"</pre>
<ul>
	<li>Confirm your environment was installed and activate it.<ul>
			<li>Type&nbsp;<code>conda env list</code>&nbsp;to display the list of your locally installed environments.
				<ul>
					<li>You should see 2 environments, including dojo-env:<ul>
							<li><code>base</code></li>
							<li><code>dojo-env</code></li>
						</ul>
					</li>
				</ul>
			</li>
		</ul>
	</li>
	<li>If you see dojo-env in the list:<ul>
			<li>Success!&nbsp; dojo-env was successfully created! But we aren't using it yet just yet. We must first
				"activate" an environment to determine which version of python &amp; packages are currently being
				used.<br>
			</li>
		</ul>
	</li>
</ul>
<h3>Activate the dojo-env</h3>
<ul>
	<li><strong>Run the conda activate command to switch to dojo-env.&nbsp;</strong></li>
</ul>
<pre data-language="ruby" class="rainbow">conda activate dojo-env</pre>
<ul>
	<li>You should now see "(dojo-env)" next to your prompt in your terminal (may be above the prompt, on the left, or
		on the right depending on your OS)</li>
</ul>
<p><strong>Troubleshooting for Windows users:</strong></p>
<ul>
	<li>&nbsp;If you see a message that says "your terminal is not set up for conda activate", you will use a slightly
		different command to activate your environment.&nbsp;Replace the word "conda" with "source".&nbsp;</li>
</ul>
<pre data-language="ruby" class="rainbow">source activate dojo-env</pre>
<p>
	<font color="#3e4e5a" face="Gotham-Rounded-Bold"><b><strong><br></strong></b></font>
</p>
<h3>
	<font color="#3e4e5a" face="Gotham-Rounded-Bold"><b><strong>
				Add dojo-env&nbsp;to jupyter notebook/lab</strong></b></font>
</h3>
<ul>
	<li>After confirming you now see (dojo-env) displayed next to your prompt:<ul>
			<li>Run the following command to make sure Jupyter Notebook/Lab knows your new environment.</li>
		</ul>
	</li>
</ul>
<pre data-language="ruby" class="rainbow">python -m ipykernel install --user --name dojo-env --display-name "Python (dojo-env)"
			</pre>
<h2>The moment of truth...&nbsp;</h2>
<p>You are all set for the next step: Testing Your&nbsp;New Environment!</p>
<p><br></p><br><hr></hr><br><p></p>
<h1>Step 2.4: Testing the Environment</h1>
<p></p>
<p><strong><dfn style="color: rgb(192, 80, 77);">TO DO NOTE: ADD SCREENSHOTS TO INDICATED PLACES BELOW</dfn></strong>
</p>
<p></p>
<p>To test that your installation and packages are working properly. We are going to run a specific Environment Testing
	notebook that is also located in the "dojo-env-setup" folder.</p>
<h2>Running the environment tester notebook with jupyter notebook</h2>
<ul>
	<li>From the same terminal window,&nbsp;start jupyter notebook&nbsp;(run&nbsp;<code>jupyter notebook</code>&nbsp;in
		your terminal)&nbsp;<ul>
			<li>A new tab should open in your web browser that shows the File view for jupyter notebook.</li>
			<li>You should see all of the files that were in the dojo-env-folder.</li>
		</ul>
	</li>
</ul>
<p><strong><dfn style="color: rgb(192, 80, 77);">TO DO: ADD SCREENSHOT HERE</dfn></strong></p>
<ul>
	<li>There are 2 "EnvironmentTester"&nbsp;notebooks:<ul>
			<li>"EnvironmentTester-mac.ipynb" for macs&nbsp;(both Intel and Apple Chip macs)</li>
			<li>"EnvironmentTester-windows.ipynb"&nbsp;for Windows.</li>
		</ul>
	</li>
</ul>
<ul>
	<li><strong>Click on the test notebook for your OS to open it.</strong>
		<ul>
			<li>Once the notebook interface has loaded, you should see a toolbar with several menu choices.</li>
		</ul>
	</li>
</ul>
<p><strong><dfn style="color: rgb(192, 80, 77);">TO DO: ADD SCREENSHOT</dfn></strong></p>
<ul>
	<li>We want to run all of the cells in this notebook and confirm it can make it to the end without errors.</li>
</ul>
<ul>
	<li><strong>To Run the Entire Notebook:</strong>
		<ul>
			<li><strong>Select the "Kernel" Menu &gt; "Restart and Run All"</strong></li>
			<li><strong>Wait patiently.&nbsp;</strong>The testing notebook is going to run through several modeling and
				EDA steps to confirm that the packages are working correctly.&nbsp;<ul>
					<li>This could take anywhere from 2-10 minutes to run.&nbsp;</li>
					<li>You will see the web browser tab icon turn to an hourglass when the notebook is running and back
						to an orange notebook icon when it is done.</li>
				</ul>
			</li>
		</ul>
	</li>
</ul>
<p></p>
<ul>
	<li><strong>Scroll down to the bottom of the notebook and confirm the cells have run:</strong>
		<ul>
			<li>Check if the very last cell printed the success message.</li>
		</ul>
	</li>
</ul>
<p><br></p>
<ul>
	<li><strong>If the entire notebook ran successfully</strong>
		<ul>
			<li>Congrats! Your dojo-env is fully functional and you can move on to the next step/lesson!</li>
		</ul>
	</li>
</ul>
<ul>
	<li>I<strong>f your notebook did not run the entire notebook successfully:</strong>
		<ul>
			<li>
				<font color="#505050" face="Gotham-Rounded-Medium">Y</font>ou need to contact your instructor or a TA
				for assistance.&nbsp;
			</li>
			<li>Before contacting them, please follow the instructions below to prepare the troubleshooting files to
				give to your instructor.</li>
		</ul>
	</li>
</ul>
<p></p>
<h3>To&nbsp;Get Help Troubleshooting Your Environment.</h3>
<div>
	<h3></h3>
	<ul>
		<li>There are 2 files that you should share with your instructor/TA<ol>
				<li>A copy of your Environment Tester notebook that error'd.</li>
				<li>A copy of "FINAL_REPORT.txt" file that is in the Troubleshooting folder of the repo.</li>
			</ol>
		</li>
	</ul>
	<ol>
		<li>To share your notebook with an instructor/TA for help:<ul>
				<li>Click File &gt; Save &amp; Checkpoint.</li>
				<li>Click File &gt; Download As &gt; Notebook (.ipynb)</li>
				<li>You web browser should save a copy of the notebook to your normal "Downloads" folder.</li>
			</ul>
		</li>
		<li>To share a copy of your FINAL_REPORT.txt:<ul>
				<li>In the first Files tab that opened when you started jupyter notebook you should see a folder called
					"Troubleshooting"</li>
				<li>Click on the troublshooting folder.</li>
				<li>Inside the folder you should have a file called "FINAL_REPORT.txt".</li>
				<li>Check the checkbox next to the file and the click on the "Download" button that appears at the top
					of the list of files.</li>
				<li>Your web browser will also save this file to your Downloads folder.&nbsp;</li>
			</ul>
		</li>
	</ol>
	<p><dfn style="color: rgb(192, 80, 77);">TO DO: ADD SCREENSHOT</dfn></p>
	<ul>
		<li>Email your instructor (and please cc:&nbsp;<a
				href="mailto:jirving@codingdojo.com">jirving@codingdojo.com</a>)<ul>
				<li>Attach the 2 files listed above.</li>
				<li>Add any additional details or info you think may be helpful for us to know.<ul>
						<li>For example:<ul>
								<li>"my computer is really old and I think that may be part of the problem."</li>
								<li>"I share this computer with someone else who also uses python"</li>
							</ul>
						</li>
					</ul>
				</li>
			</ul>
		</li>
		<li>An instructor or TA will get back to you within 24 hours (at most) with the next steps for you to try.<ul>
				<li>You will most likely need to set up a Zoom call and share your screen for us to help.</li>
			</ul>
		</li>
	</ul>
</div><br><hr></hr><br><h1>Step 2.5: Setting dojo-env as the default + alias commands</h1>
<ul>
	<li>This section will require you to enter several commands in your Terminal (on Mac) or GitBash (on Windows).<ul>
			<li>Make sure that your terminal is not running jupyter notebook (you can press
				"<code>Cntrl</code>+<code>C</code>" to force quit the server from your terminal).</li>
		</ul>
		<ul>
			<li>Alternatively, you can open a new terminal/GitBash. (You can perform these steps from any folder.)</li>
		</ul>
	</li>
</ul>
<h1>Commands For Mac OS&nbsp;</h1>
<ul>
	<li>All mac users should follow these instructions&nbsp;(regardless of if your have an Intel or Apple processor).
	</li>
	<li>On a Mac, we need to first see what shell terminal is using.&nbsp;&nbsp;<ul>
			<li>There are 2 possible options that your mac may be using:<ul>
					<li>&nbsp;zsh</li>
					<li>bash</li>
				</ul>
			</li>
		</ul>
	</li>
	<li>T<strong>he major difference between zsh and bash is which file it checks for the settings&nbsp;</strong>to use
		when you create a new terminal.<ul>
			<li>Otherwise, zsh and bash behave very similarly and you may not notice the difference if you switched.
			</li>
		</ul>
	</li>
</ul>
<p><br></p>
<h2>Determining If your Shell is Bash or Zsh</h2>
<ul>
	<li>In your terminal, type&nbsp;<code>echo $SHELL.</code>&nbsp;and hit enter.</li>
</ul>
<h3>If the response ends in&nbsp;bash</h3>
<ul>
	<li><strong>Run the following commands to automatically activate dojo-env</strong></li>
</ul>
<pre data-language="ruby" class="rainbow">touch ~/.bash_profile
			echo "conda activate dojo-env" &gt;&gt; ~/.bash_profile</pre>
<ul>
	<li><strong>Run the following 2 commands to add shortcuts for opening jupyter</strong>
		<ul>
			<li><strong>NOTE: it is VERY important that you do not add any spaces on either side of
					the&nbsp;<code>=</code>&nbsp;sign</strong>.&nbsp;The command will not work correctly if you add
				extra spaces.</li>
		</ul>
	</li>
</ul>
<pre data-language="ruby" class="rainbow">echo 'alias jnb="jupyter notebook"' &gt;&gt; ~/.bash_profile
			echo 'alias lab="jupyter lab"' &gt;&gt; ~/.bash_profile</pre>
<p><br></p>
<h3>If the response ends in&nbsp;zsh:</h3>
<h3></h3>
<ul>
	<li>Run the following commands to automatically activate dojo-env</li>
</ul>
<pre class="rainbow" data-language="ruby">touch ~/.zshrc
			echo "conda activate dojo-env" &gt;&gt; ~/.zshrc</pre>
<ul>
	<li>Run the following 2 commands to add shortcuts for opening jupyter<ul>
			<li>NOTE: it is VERY important that you do not add any spaces on either side of
				the&nbsp;<code>=</code>&nbsp;sign.&nbsp;The command will not work correctly if you add extra spaces.
			</li>
		</ul>
	</li>
</ul>
<pre class="rainbow" data-language="ruby">echo 'alias jnb="jupyter notebook"' &gt;&gt; ~/.zshrc
			echo 'alias lab="jupyter lab"' &gt;&gt; ~/.zshrc</pre>
<p><br></p>
<h1>Commands for Windows</h1>
<p>
	For windows computers,<strong> we need to determine if your computer uses the word "conda" or "source" to activate
		an environment</strong>.</p>
<ul>
	<li>You've already run this command before, but if you don't remember which command you ran:<ul>
			<li><strong>Run the "conda activate base" or "conda activate dojo-env" command in gitbash.</strong>
				<ul>
					<li><strong>If you see a message about your shell not being set up to run conda activate,</strong>
						<ul>
							<li>You need to <strong>use the "source activate commands"</strong> section below</li>
						</ul>
					</li>
					<li><strong>If the conda activate command worked,&nbsp;</strong>
						<ul>
							<li>
								<font color="#505050" face="Gotham-Rounded-Medium">F</font>ollow the <strong>"conda
									activate commands" </strong>section below.
							</li>
						</ul>
					</li>
				</ul>
			</li>
		</ul>
	</li>
</ul>
<p>
	<font color="#c7254e" face="Consolas, Menlo, Monaco, Courier New, monospace"><br></font>
</p>
<h2>conda activate commands:</h2>
<ul>
	<li>Run the following commands to automatically activate dojo-env</li>
</ul>
<pre class="rainbow" data-language="ruby">touch ~/.bash_profile
			echo "conda activate dojo-env" &gt;&gt; ~/.bash_profile</pre>
<ul>
	<li>Run the following 2 commands to add shortcuts for opening jupyter<ul>
			<li>NOTE: it is VERY important that you do not add any spaces on either side of
				the&nbsp;<code>=</code>&nbsp;sign.&nbsp;The command will not work correctly if you add extra spaces.
			</li>
		</ul>
	</li>
</ul>
<pre class="rainbow" data-language="ruby">echo 'alias jnb="jupyter notebook"' &gt;&gt; ~/.bash_profile
			echo 'alias lab="jupyter lab"' &gt;&gt; ~/.bash_profile</pre>
<p><br></p>
<p><br></p>
<ol>
	<li>Make sure the profile file for GitBash has been created.<ul>
			<li>Run&nbsp;<code>touch ~/.bash_profile</code>&nbsp;to create a new hidden file called ".bash_profile" in
				your user folder.</li>
		</ul>
	</li>
	<li>Add the environment activation command.<ul>
			<li>Run&nbsp;<code>echo "conda activate dojo-env" &gt;&gt; ~/.bash_profile</code></li>
		</ul>
	</li>
	<li>Add the alias to start "jupyter notebook" using&nbsp;<code>jnb</code>
		<ul>
			<li><strong>NOTE: it is VERY important that you do not add any spaces on either side of
					the&nbsp;<code>=</code>&nbsp;sign.</strong>&nbsp;The command will not work correctly if you add
				extra spaces.</li>
			<li>Run&nbsp;<code>echo 'alias jnb="jupyter notebook"' &gt;&gt; ~/.bash_profile</code></li>
		</ul>
	</li>
	<li>Finally, activate the new settings:<ul>
			<li>Run&nbsp;<code>source ~/.bash_profile</code>&nbsp;to activate the changes you just made</li>
		</ul>
	</li>
</ol>
<h2>source activate commands:</h2>
<ol>
	<li>Make sure the profile file for GitBash has been created.<ul>
			<li>Run&nbsp;<code>touch ~/.bash_profile</code>&nbsp;to create a new hidden file called ".bash_profile" in
				your user folder.</li>
		</ul>
	</li>
	<li>Add the environment activation command.<ul>
			<li>Run&nbsp;<code>echo "source activate dojo-env" &gt;&gt; ~/.bash_profile</code></li>
		</ul>
	</li>
	<li>Add the alias to start "jupyter notebook" using&nbsp;<code>jnb</code>
		<h2></h2>
		<ul>
			<li><strong>NOTE: it is VERY important that you do not add any spaces on either side of
					the&nbsp;<code>=</code>&nbsp;sign.</strong>&nbsp;The command will not work correctly if you add
				extra spaces.</li>
			<li>Run&nbsp;<code>echo 'alias jnb="jupyter notebook"' &gt;&gt; ~/.bash_profile</code></li>
		</ul>
	</li>
	<li>Finally, activate the new settings:<ul>
			<li>Run&nbsp;<code>source ~/.bash_profile</code>&nbsp;to activate the changes you just made</li>
		</ul>
	</li>
</ol>
<p></p>
<h1>Final Verification Steps&nbsp;(Mac &amp; Windows)</h1>
<h3>Confirm&nbsp;<code>dojo-env</code>&nbsp;is your default</h3>
<ul>
	<li>To confirm that&nbsp;<code>dojo-env</code>&nbsp;is now your default environment:<ul>
			<li>Open a new Terminal/GitBash window.</li>
			<li>You should see&nbsp;<code>(dojo-env)</code>&nbsp;appear next to your prompt.</li>
		</ul>
	</li>
</ul>
<h2>
</h2>
<figure><img
		src="https://s3.us-east-1.amazonaws.com/General_V88/boomyeah2015/codingdojo/curriculum/content/chapter/1647634446__confirm_dojo_env.png"
		style="width: 454px; height: 100px;" width="454" height="100"></figure>
<h2></h2>
<p>
</p>
<h3>Confirm the shortcut aliases work</h3>
<div>
	<ul>
		<li>
			<font color="#505050"><strong>Try running the command "jnb" in your terminal/gitbash.</strong></font>
			<ul>
				<li>
					<font color="#505050">&nbsp;If jupyter notebook launches, you're all set!</font>
				</li>
			</ul>
			<ul>
				<li>
					<font color="#505050">If not, contact your instructor or a TA for assitance.</font>
				</li>
			</ul>
		</li>
	</ul>
	<h2>Note: you can still move on to the next step even if you could not successfully complete this step.</h2>
	<ul>
		<li>These steps are for convenience and are not strictly required.</li>
		<li>You should still contact your instructor or a TA for assistance to successfully complete this step at your
			earliest convenience.</li>
	</ul>
	<h2></h2>
	<h2> <br>

	</h2>
</div><br><hr></hr><br><h1>Step 2.6 Adding nbextensions</h1>
<h1>Jupyter Notebook Extensions Resources</h1>
<ul>
	<li><a href="https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/install.html">Documentation</a></li>
	<li><a href="https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/install.html">Official
			<code>nbextensions</code> Installation Instructions (also detailed below)</a></li>
</ul>
<h4>Installing Using Pip</h4>
<ul>
	<li><strong>Below is an abbreviated version of the official instructions for Installing jupyter-contrib-nbextensions
			(<a
				href="https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/install.html">Documentation</a>):</strong>
		<ol>
			<li>Install extensions</li>
		</ol>
		<pre data-language="language-bash rainbow" class="rainbow">pip install jupyter_contrib_nbextensions
			</pre>
		<ol start="2">
			<li>Install additional requirements (Install javascript and css file):</li>
		</ol>
		<pre data-language="language-bash rainbow" class="rainbow">jupyter contrib nbextension install --user
			</pre>
		<ol start="3">
			<li>Activate the extension configurator</li>
		</ol>
		<pre data-language="language-bash rainbow" class="rainbow">jupyter nbextension enable jupyter_nbextensions_configurator
			</pre>
	</li>
</ul>
<blockquote>
	<ul>
		<li>Now, boot up jupyter notebook and look for a new tab called (<code>nbextensions</code>) on the jupyter
			file-explorer view. If its there, great! Move on to the "Turning on extensions" section below.</li>
	</ul>
</blockquote>
<p></p>
<figure><img
		src="https://s3.us-east-1.amazonaws.com/General_V88/boomyeah2015/codingdojo/curriculum/content/chapter/1657134126__nbextension_tab.png"
		style="width: 304px; height: 87px;" width="304" height="87"></figure>
<p></p>
<h2>Activating Specific Extensions:</h2>
<h3>
	<div></div>
</h3>
<ul>
	<li>
		<p><strong>When you boot up jupyter notebook, there should be a new tab at the top called
				<code>nbextensions</code>.</strong> Click on the tab to open the list of available extensions.</p>
	</li>
	<li>
		<p>This opens a menu of all of the available extensions with checkboxes to activate them;</p>
		<ul>
			<li><em><strong>NOTE: If the list of available notebook extensions is grayed out like the screenshot below:
						<p><br></p>
						<figure><img
								src="https://s3.us-east-1.amazonaws.com/General_V88/boomyeah2015/codingdojo/curriculum/content/chapter/1657134336__nbextensions_disabled.png"
								style="width: 818px; height: 291px;" width="818" height="291"></figure><br>
					</strong></em>
				<ul>
					<li>Uncheck
						"<code>disable configuration for nbextensions without explicit compatibility (they may break your notebook environment, but can be useful to show for nbextension development)</code>"
						at the top of the page next to the search box.</li>
				</ul>
			</li>
		</ul>
	</li>
</ul>
<ul>
	<li>
		<p><strong>To enable the recommended extensions</strong>:</p>
		<ul>
			<li>Click on the <strong>checkbox</strong> next to the extensions name to activate the extension.</li>
		</ul>
	</li>
</ul>
<ul>
	<li>
		<p><strong>To change the settings for an extension</strong>:</p>
		<ul>
			<li>Click on the <strong>name</strong> of the extension to select it. Now, if you scroll down, you should
				see the list of options for the currently selected extension.</li>
		</ul>
		<p><br></p>
		<figure><img
				src="https://s3.us-east-1.amazonaws.com/General_V88/boomyeah2015/codingdojo/curriculum/content/chapter/1657135650__click_name_to_show_settings.png"
				style="width: 658px; height: 231px;" width="658" height="231"></figure>
	</li>
	<li>
		<p><strong>Note: any extensions that you enable or settings that you change are <em>automatically</em>
				saved.</strong></p>
	</li>
</ul>
<p><br></p>
<h2>Recommended Extensions &amp; Settings</h2>
<p>The following section will walk you through each of the recommended extensions and their recommended settings.&nbsp;
</p>
<p>Brief Summary of&nbsp;Extensions to Enable</p>
<ul>
	<li>Table of Contents (2)</li>
	<li>Collapsible Headings</li>
	<li>Live Markdown Preview&nbsp;</li>
	<li>Ruler&nbsp;</li>
	<li>spellchecker</li>
</ul>
<p><br><br></p>
<h3>1. Table of Contents&nbsp;(2):</h3>
<div>
	<ul>
		<li>
			<p>Clickable sidebar with markdown headers as bookmarks/links.<br></p>
		</li>
		<li>Recommended options:<p><br></p>
			<ul>
				<li>Uncheck Automatically number notebook sections</li>
				<li>Change <code>Maximum level of nested sections to display on the tables of contents</code> to 3.</li>
				<li>Check <code>Display Table of Contents as a sidebar (otherwise as a floating window)</code></li>
				<li>Check
					<code>Collapse/uncollapse ToC sections when the collapsible_headings nbextension is used to collapse/uncollapse sections in the notebook. For the inverse behaviour, see collapsible_headings' configuration</code>
				</li>
			</ul>
		</li>
	</ul>
	<figure><img
			src="https://s3.us-east-1.amazonaws.com/General_V88/boomyeah2015/codingdojo/curriculum/content/chapter/1657134622__toc2_settings.png"
			style="width: 667px; height: 466px;" width="667" height="466"></figure>
	<p><br></p>
	<h3>2. Collapsible Headings</h3>
</div>
<ul>
	<li>Collapse sections of your notebook using markdown headers.</li>
	<li>Recommended options:<ul>
			<li>Check 'Collapse/uncollapse notebook sections when the ToC2 nbextension is used to collapse/uncollapse
				sections in the table of contents. For the inverse behaviour, see ToC2's configuration' at towards the
				bottom of the options.</li>
			<li><img src="https://s3.us-east-1.amazonaws.com/General_V88/boomyeah2015/codingdojo/curriculum/content/chapter/1657135109__collapsible_headings_settings.png"
					width="596" height="188" style="width: 596px; height: 188px;"></li>
		</ul>
	</li>
</ul>
<div>
	<p></p>
	<h3>3. Live Markdown&nbsp;Preview</h3>
</div>
<div>Shows a preview of what the markdown cell you are editing will look like once you render it with Shift+Enter<ul>
		<li>
			<ul>
				<li>Recommended options:
					<ul>
						<li>Check
							<code>Show the input &amp; output of markdown cells side-by-side while editing them.</code>
						</li>
					</ul>
				</li>
			</ul>
		</li>
	</ul>
	<figure><img
			src="https://s3.us-east-1.amazonaws.com/General_V88/boomyeah2015/codingdojo/curriculum/content/chapter/1657135333__live_md_preview_settings.png">
	</figure>
	<p></p>
	<p>
		<font color="#3e4e5a" face="Gotham-Rounded-Bold"><b>4. Ruler (not Ruler in&nbsp;Editor)</b></font>
	</p>
	<ul>
		<li>Adds a vertical red line in code cells at 80 characters. Python code should not cross this line (to match
			Python's style guide)</li>
		<li>Settings:<ul>
				<li>No settings to change.</li>
			</ul>
		</li>
	</ul>
	<h3>5. spellchecker&nbsp;</h3>
</div>
<div><b><strong></strong><strong></strong><strong>Checks markdown cells for spelling and highlights words in red that
			are misspelled. Note: it cannot correct misspelled words, only highlight them.</strong></b></div>
<div>
	<h3><span></span></h3>
	<h3></h3>
	<h2>Confirming Extensions are Enabled</h2>
	<h2></h2>
	<ul>
		<li><strong>Go back to the Files tab and create a new notebook with the&nbsp;<code>New</code>&nbsp;button on the
				top-right.</strong>
			<ul>
				<li>Select&nbsp;<code>Python(dojo-env)</code>&nbsp;for your kernel&nbsp;<p><br><img
							src="https://s3.us-east-1.amazonaws.com/General_V88/boomyeah2015/codingdojo/curriculum/content/chapter/1647634592__new_notebook.png"
							style="width: 539px; height: 187px;" width="539" height="187"><br><br></p>
					<p><br></p>
					<figure></figure>
				</li>
			</ul>
		</li>
		<li><strong>Once your new Untitled notebook opens, you will notice a few new elements to the
				interface</strong>:&nbsp;<p><br><img
					src="https://s3.us-east-1.amazonaws.com/General_V88/boomyeah2015/codingdojo/curriculum/content/chapter/1647634606__nbextensions_interface.png"
					style="width: 698px; height: 156px;" width="698" height="156"></p>
			<p><br></p>
			<figure></figure>
		</li>
		<li><strong>First, confirm that you have two new buttons on your toolbar</strong>:<ul>
				<li>One that looks like a list (this is your table of contents extension)</li>
				<li>One that looks like a checkmark (this is your spellchecker)</li>
			</ul>
		</li>
		<li><strong>Second, confirm that you see a red dashed line in your code cell. (the Ruler extension)</strong>
		</li>
		<li><strong>Third, click on the button for the table of contents (the one that looks like a list).</strong>
			<ul>
				<li>An empty sidebar should appear on the left.</li>
			</ul>
		</li>
		<li><strong>Fourth, change your code cell to a markdown cell</strong>.<ul>
				<li>You can click on the dropdown menu on your toolbar that currently says "code".<ul>
						<li>Change this to Markdown.</li>
						<li>In the markdown cell, type the following text but do NOT run the cell yet.</li>
						<li><code># TEST HEEDER</code>&nbsp;(misspelled on purpose).</li>
					</ul>
				</li>
			</ul>
		</li>
	</ul>
	<figure><img
			src="https://s3.us-east-1.amazonaws.com/General_V88/boomyeah2015/codingdojo/curriculum/content/chapter/1647634678__nbextensions_toc_preview_spellcheck.png">
	</figure>
	<p>&nbsp;</p>
	<ul>
		<li><strong>Confirm that you see a preview of your markdown text off to the right.</strong>&nbsp;<ul>
				<li>&nbsp;this is your Live Markdown Preview extension.&nbsp;</li>
			</ul>
		</li>
		<li><strong>Confirm that the word "HEEDER" is highlighted in red.</strong>&nbsp;<ul>
				<li>This is your spellchecker.</li>
			</ul>
		</li>
		<li><strong>Finally, run the cell "Shift+Enter" and confirm</strong>:<ul>
				<li>that the header appears in the table of contents on the left.</li>
				<li>that a dropdown arrow appears to the left of the header in the notebook.&nbsp;<p><br></p>
					<p><br></p>
					<figure><img
							src="https://s3.us-east-1.amazonaws.com/General_V88/boomyeah2015/codingdojo/curriculum/content/chapter/1647634746__toc_collapse_headings.png">
					</figure>
				</li>
			</ul>
		</li>
		<li>You may notice that the ToC automatically numbered the header and added&nbsp;<code>1</code>&nbsp;next to
			Test Heeder.<ul>
				<li>If you prefer to disable this, click on the small gear icon next to the word Contents:&nbsp;<p><br>
					</p>
					<p><br></p>
					<figure><img
							src="https://s3.us-east-1.amazonaws.com/General_V88/boomyeah2015/codingdojo/curriculum/content/chapter/1647634778__toc_settings.png"
							style="width: 351px; height: 262px;" width="351" height="262"></figure>
				</li>
				<li>In the menu that appears, uncheck "Automatically number headings"&nbsp;<p><br></p>
					<p><br></p>
					<figure><img
							src="https://s3.us-east-1.amazonaws.com/General_V88/boomyeah2015/codingdojo/curriculum/content/chapter/1647634797__turn_off_numbered_headers.png"
							style="width: 506px; height: 287px;" width="506" height="287"></figure>
				</li>
			</ul>
		</li>
	</ul>
	<h4></h4>
	<blockquote><strong>Now you are all set with your Jupyter Notebook extensions! Onto the final step 5. Install a Code
			Editor -&nbsp;VS Code.</strong></blockquote>
	<p> <br> <br> <br> <br> <br> </p>
	<p> <br> <br></p>
</div><br><hr></hr><br><h1>2. Setting Up Your dojo-env Environment</h1>
<h2>Step 2 Overview:</h2>
<ul>
    <li><strong>In Step 1, we installed the foundational tools needed for our local python installation.&nbsp;</strong>
        <ul>
            <li>While we did install a Python distribution with a basic copy of Python (Anaconda or miniforge), we have
                not installed all of the packages and tools that we need as data scientists.</li>
        </ul>
    </li>
    <li><strong>In Step 2, you will be creating a custom python environment called "dojo-env".&nbsp;</strong>
        <ul>
            <li><strong>An "environment" is a bundle of specific python packages that are used together.</strong>
                Importantly, an environment specifies specific version #'s of the packages to ensure that all of the
                versions installed are mutually compatible.</li>
            <li><strong>You can install many environments</strong> on your computer and switch between them as needed
                for different projects.</li>
        </ul>
        <ul>
            <li><strong>We have designed the dojo-env to include everything you'd need for our program</strong>, so you
                may not have a reason to add additional environments.&nbsp;</li>
        </ul>
    </li>
</ul>
<h3>Currently Supported Operating Systems</h3>
<h3></h3>
<ul>
    <li><strong>We have prepared environment files (.yml files) for 3 different OS configurations:</strong>
        <ul>
            <li><strong>Windows (10 &amp; 11)</strong></li>
            <li><strong>Mac (with Intel processors)</strong></li>
            <li><strong>Mac (Apple Chips).&nbsp;<br></strong></li>
        </ul>
    </li>
    <li>&nbsp;Reminder for mac users:&nbsp;&nbsp;<ul>
            <li>Please revisit the "1.&nbsp;Downloading and Installing Apps" lesson if you are not sure which type of
                mac you are using.</li>
        </ul>
    </li>
    <li>Note to Linux Users:<ul>
            <li>Sorry Linux users! A Linux machine was not available for testing during the development of the
                dojo-env.&nbsp;</li>
            <li>If you are willing to work with an instructor to develop and test a Linux version of dojo-env, contact
                your instructor or send an email to jirving@codingdojo.com requesting assistance in create a linux
                version of dojo-env.</li>
        </ul>
    </li>
    <li><strong>The environment files (and a backup of these instructions) are in the dojo-env-setup repository</strong>
        (<a
            href="https://github.com/coding-dojo-data-science/dojo-env-setup">https://github.com/coding-dojo-data-science/dojo-env-setup</a>)
        <ul>
            <li>The Detailed Instructions below will guide you through how to clone and use the environment setup
                repository.</li>
        </ul>
    </li>
</ul>
<p><br></p>
<h2>Brief Summary of the Following Steps:</h2>
<ul>
    <li>Step 2.1:&nbsp; Clone the dojo-env-setup repository</li>
    <li>Step 2.2:&nbsp;Open the repo in your terminal/GitBash</li>
    <li>Step 2.3:&nbsp;Create the dojo-env environment</li>
    <li>Step 2.4: Setting dojo-env as your default.</li>
</ul>
<h1></h1><br><hr></hr><br><h1>Step 3: Install a Code Text Editor </h1>
<h2>Visual Studio Code</h2>
<ul>
	<li>The final tool to install is a text editor that is designed for programmers.<ul>
			<li>There are several text editors available, but we will be using Visual&nbsp;Studio&nbsp;Code.</li>
		</ul>
	</li>
	<li><strong>Visual&nbsp;Studio Code (A.K.A&nbsp; "VS Code")&nbsp;</strong>is a free editor that is highly
		customizable and supports many languages.<ul>
			<li>It is maintained by Microsoft and has a robust community of extensions and add-ons.</li>
			<li>It is very popular and is used by many companies (e.g.&nbsp;Facebook/Meta)</li>
		</ul>
	</li>
</ul>
<p></p>
<ul>
	<li><strong>How will we use VS Code?</strong>
		<ul>
			<li>
				<font color="#505050" face="Gotham-Rounded-Medium"><strong>We could technically run all of our jupyter
						notebooks using VS Code, but this is not recommended </strong>at this point in your education
				</font>.&nbsp;<ul>
					<li>While VS Code is convenient for quickly opening and working with a repository or viewing a
						notebook, it has some limitations in how notebooks look and some quirks to the interface for
						notebooks.</li>
				</ul>
				<ul>
					<li>Instead, we will focus on using<strong> jupyter notebook or jupyter lab in the lessons and live
							class.</strong>
						<ul>
							<li>You are welcome to try VS Code for notebooks, but it is recommended you become
								comfortable with jupyter first.</li>
						</ul>
					</li>
				</ul>
			</li>
		</ul>
	</li>
	<li><strong>We will use VS Code for editing simple code files or hidden files.</strong><br>
		<ul>
			<li>We can open and edit the settings file for your terminal&nbsp; (e.g.:&nbsp;
				"<code>~/.bash_profile"</code>.or "~/.zshrc"</li>
		</ul>
		<ul>
			<li>We will use it to create and store credentials for APIs (Stack 4)</li>
			<li>We can use VS Code to edit your projects' README files while previewing them in real time!</li>
			<li>Finally, while beyond the scope of the standard curriculum, we can also use VS Code to store functions
				in external files that we can use just like pandas, matplotlib,</li>
		</ul>
	</li>
</ul>
<p><br></p>
<ul></ul>
<h2>Install Visual Studio Code</h2>
<ul>
	<li>
		<p>Go to <a href="https://code.visualstudio.com/">https://code.visualstudio.com/</a></p>
		<ul>
			<li>It should auto-recognize your OS and have a blue Download button with a version for your OS.</li>
			<li>Click Download to download the installer.</li>
		</ul>
	</li>
	<li>
		<p>For Windows Users:</p>
		<ul>
			<li>Click on the installer to run it.</li>
			<li>Select the default options.</li>
		</ul>
	</li>
	<li>
		<p>For Mac Users:</p>
		<ul>
			<li>Click on the installer to unzip it.</li>
			<li>Once the Application is unzipped, drag the icon for Visual Studio Code.app to your applications folder
				on your sidebar in Finder.<br><br>&nbsp;&nbsp;<img
					src="https://raw.githubusercontent.com/coding-dojo-data-science/dojo-env-setup/main/images/mac_vscode_install.png"
					alt="png" width="424" height="115" style="color: rgb(80, 80, 80); width: 424px; height: 115px;">
			</li>
		</ul>
	</li>
</ul>
<ul>
	<li>
		<p>Once Visual Studio Code installation is completed, open it!</p>
		<ul>
			<li>Windows Users: check your Start Menu.</li>
			<li>Mac Users: check your Applications folder in Finder.</li>
		</ul>
	</li>
</ul>
<p><img src="https://raw.githubusercontent.com/coding-dojo-data-science/dojo-env-setup/main/images/vs_code_get_started.png"
		alt="png" style="width: 644px; height: 486px;" width="644" height="486"></p>
<h2>Install Python Extensions</h2>
<ul>
	<li>On the left sidebar, there are several icons for different menus.</li>
	<li>Click on the Extensions sidebar icon (5th down, looks like 4 squares).</li>
</ul>
<p><img src="https://raw.githubusercontent.com/coding-dojo-data-science/dojo-env-setup/main/images/1_extension_sidebar.png"
		alt="png" style="width: 598px; height: 450px;" width="598" height="450"></p>
<ul>
	<li>
		<p>On the Extension sidebar, there will be several sections (INSTALLED/POPULAR/RECOMMENDED).</p>
		<ul>
			<li>
				<p>Right now you should have nothing under the INSTALLED menu.</p>
			</li>
			<li>
				<p>You should see "Python" listed under POPULAR.</p>
				<ul>
					<li>If not, you can enter "Python" in the search box at the top of the sidebar</li>
					<li>OR you can click on <a
							href="https://marketplace.visualstudio.com/items?itemName=ms-python.python">this link to the
							extension </a> on the extension marketplace website.</li>
				</ul>
			</li>
			<li>
				<p>Click on the "Install" button for the Python extension.<br>
					<img src="https://raw.githubusercontent.com/coding-dojo-data-science/dojo-env-setup/main/images/2_extension_installation.png"
						alt="png" style="width: 249px; height: 617px;" width="249" height="617">
				</p>
			</li>
		</ul>
	</li>
	<li>
		<p>Note: the Python extension will also install several required extensions. When installation is complete, you
			should see the following under the "INSTALLED" section:</p>
		<ul>
			<li>Python, Pylance, Jupyter Notebook renderer, Jupyter, and Jupyter Keymap</li>
		</ul>
	</li>
</ul>
<p><img src="https://raw.githubusercontent.com/coding-dojo-data-science/dojo-env-setup/main/images/3_installed_extensions.png"
		alt="png" style="width: 508px; height: 380px;" width="508" height="380"></p>
<h2>Setting VS Code to use your <code>dojo-env</code> as the default Python installation</h2>
<ul>
	<li>
		<p>We must teach the Python extension where to find our <code>dojo-env</code>'s version of Python.</p>
	</li>
	<li>
		<p>On the extension sidebar, click on the Gear icon for the Python extension and select "Extension Settings"
			<img src="https://raw.githubusercontent.com/coding-dojo-data-science/dojo-env-setup/main/images/4_python_settings.png"
				alt="png" style="width: 455px; height: 393px;" width="455" height="393">
		</p>
	</li>
	<li>
		<p>You should see a new "Settings" pane open in the main window.</p>
		<ul>
			<li>Take note of the "Default Interpreter Path".
				<ul>
					<li>It is currently set to just "python".<br>
						<img src="https://raw.githubusercontent.com/coding-dojo-data-science/dojo-env-setup/main/images/5_settings_default_interp.png"
							alt="png" style="width: 612px; height: 530px;" width="612" height="530">
					</li>
				</ul>
			</li>
		</ul>
	</li>
	<li>
		<p>We need to change this setting to match the exact filepath for our <code>dojo-env</code>'s python.</p>
	</li>
	<li>
		<p>In your terminal or GitBash:</p>
		<ul>
			<li>Make sure your dojo-env is activated</li>
			<li>Run the command: <code>which python</code>
				<ul>
					<li>It will print out a filepath to your dojo-env.<br>
						<img src="https://raw.githubusercontent.com/coding-dojo-data-science/dojo-env-setup/main/images/6_which_python.png"
							alt="png" style="width: 413px; height: 269px;" width="413" height="269">
					</li>
				</ul>
			</li>
			<li>Copy and paste that exact file path into the "Default Interpreter Path" field in the Python extension
				settings.</li>
		</ul>
	</li>
</ul>
<p><img src="https://raw.githubusercontent.com/coding-dojo-data-science/dojo-env-setup/main/images/7_replace_default_interp.png"
		alt="png" style="width: 461px; height: 149px;" width="461" height="149"></p>
<h3>Mac Users Only: Add the <code>code</code> command to your terminal</h3>
<ul>
	<li>We want to be able to type the word "code" in our terminal and have that open up VS Code.
		<ul>
			<li>
				<p>Windows users have this command added automatically during installation.</p>
			</li>
			<li>
				<p>Mac Users must run 1 more command from VS Code.</p>
			</li>
		</ul>
	</li>
</ul>
<ol>
	<li>
		<p>Open the Command Palette:</p>
		<ul>
			<li>Either click on View in the menu bar and select "Command Palette"</li>
			<li>OR use the keyboard shortcut (<code>Cmd</code> + <code>Shift</code> +<code>p</code>)</li>
		</ul>
	</li>
	<li>
		<p>In the small pop-up window, type "install code" and you should see it auto-suggest the option for "Shell
			Command: Install 'code' command in PATH".</p>
		<ul>
			<li>Click on this option.</li>
		</ul>
	</li>
</ol>
<p><img src="https://raw.githubusercontent.com/coding-dojo-data-science/dojo-env-setup/main/images/8_install_code_command.png"
		alt="png" style="width: 533px; height: 80px;" width="533" height="80"></p>
<h3>Test the <code>code</code> command</h3>
<ul>
	<li>
		<p>Open a new terminal or GitBash window.</p>
	</li>
	<li>
		<p>Run the command <code>code</code> to verify that VS Code opens.</p>
	</li>
	<li>
		<p>Note: You can add a specific folder or filename to open, after the word code.</p>
		<ul>
			<li>To open the current folder <code>code .</code></li>
		</ul>
	</li>
	<li>
		<p>If it opens, great!</p>
		<ul>
			<li>If not, make sure you've opened a new terminal window AFTER installing the code command.</li>
		</ul>
	</li>
</ul>
<blockquote><strong>Congratulations! You are all set up with your local python environment!&nbsp;<br></strong>You may
	want to read the Final&nbsp;Notes + Appendix lesson so that you are aware of the contents, in case you need
	them.<strong></strong></blockquote>
<p> <br> <br> <br> </p>
<p> <br> <br></p><br><hr></hr><br><h1>Final Notes</h1>
<h2></h2>
<p><strong>Congrats! You've got a fully functional professional data science environment on your local machine!</strong>
</p>
<ul>
	<li><strong>Please see the next chapter "Working Locally" for:</strong>
		<ul>
			<li>&nbsp;a walkthrough of how to use your new local installation and tools together</li>
			<li>&nbsp;a summary of terminal commands</li>
			<li>jupyter notebook chgeat sheets</li>
			<li>how to install additional packages</li>
			<li>&nbsp;&amp; more!</li>
		</ul>
	</li>
</ul>
<ul>
	<li><strong>Please see the "Troubleshooting" chapter for commonly encountered errors and any known solutions.
			including:</strong>
		<ul>
			<li>Reinstalling your dojo-env</li>
			<li>"code" command not working</li>
			<li>GitBash "Could not fork child process" error</li>
		</ul>
	</li>
</ul><br><hr></hr><br><p> <br> </p>
<p>
</p>
<h1>Updating to New dojo-env</h1>
<ul>
	<li>If you have already installed your dojo-env and wish to update to the new version, you must first remove the
		current dojo-env from your computer.<ul>
			<li><strong>Note: the new version of dojo-env was released in July 2022. </strong>If you installed your
				environment in July or later you already have the updated dojo-env.</li>
		</ul>
	</li>
	<li><strong>The benefits of upgrading to the new dojo-env:</strong>
		<ul>
			<li>New sklearn v1.1 with simplified column transformer feature names!</li>
			<li>Jupyter Lab added</li>
		</ul>
	</li>
	<ul>
		<li>New Packages and Tools Included:</li>
		<ul>
			<li>nbdime: Version control for jupyter notebooks.&nbsp;</li>
			<li>Model Explainer Packages (SHAP, Lime, Yellowbrick)</li>
			<li>Stack 2 &amp; 3 Packages Previously Not Included:<ul>
					<li>Tensorflow</li>
					<li>xgboost</li>
					<li>lightbgm</li>
				</ul>
			</li>
			<li>Pandas Profiling (incredibly powerful all-in-one EDA report)</li>
			<li>Time Series Modeling:<ul>
					<li>pmdarima</li>
					<li>prohpet</li>
					<li>sktime (though still some issues to resolve)</li>
				</ul>
			</li>
			<li>And more!</li>
		</ul>
	</ul>
</ul>
<h4>IMPORTANT NOTE FOR MAC USERS WITH AN APPLE CHIP (M1, M1Pro, M2, etc)!</h4>
<p>The original v1 of dojo-env did not fully support Apple processors, but the new dojo-env does. HOWEVER, in order to
	do so, <strong>Mac users with an Apple chip need to UNINSTALL ANACONDA and switch to using
		Miniforge</strong>.&nbsp;&nbsp;</p>
<p>Please see Step 1 - MacOS (Apple Chip) for detailed instructions on how to uninstall anaconda and install miniforge.
</p>
<h4></h4>
<h2>Step 1: Remove Your Old dojo-env</h2>
<ul>
	<li>
		<ol>
			<li>Open your terminal/GitBash</li>
			<li>Deactivate<code>dojo-env</code>:&nbsp;<ol>
					<li>Type&nbsp;<code>conda activate base</code>&nbsp;(or source activate base if you are on older
						versions of windows)&nbsp;<ol>
							<li>Your terminal should now say&nbsp;<code>(base)</code>&nbsp;next to your prompt instead
								of&nbsp;<code>(dojo-env)</code>.</li>
						</ol>
					</li>
				</ol>
			</li>
			<li>Remove the old&nbsp;<code>dojo-env</code>&nbsp;using the command:</li>
		</ol>
	</li>
</ul>
<pre class="rainbow" data-language="ruby">conda remove --name dojo-env --all
</pre>
<p>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Enter&nbsp;<code>y</code>&nbsp;to approve the removal of the environment
	and hit enter.<br></p>
<p>&nbsp; &nbsp; &nbsp; 4. Wait for the env to be removed.</p>
<p>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; This will delete all of the files associated
	with JUST our&nbsp;<code>dojo-env</code>.&nbsp;</p>
<p>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Anaconda &amp; GitBash will still be
	installed.&nbsp; We will just need to re-install our&nbsp;<code>dojo-env</code></p>
<p><br></p>
<h2>Step 2: Clone (or update) the dojo-env-setup repo&nbsp;</h2>
<ol>
	<li>Navigate to the dojo-env-setup repo:&nbsp;<a href="https://github.com/coding-dojo-data-science/dojo-env-setup"
			target="_blank">https://github.com/coding-dojo-data-science/dojo-env-setup</a></li>
	<li><strong>Clone the Repository to Your Computer:</strong>
		<ol>
			<li>Click the green Code button and select&nbsp; "Open in GitHub&nbsp;Desktop. "</li>
			<li>If you still have your previously cloned copy, GitHub Desktop should show a # and down arrow on the top
				right corner where it should say "Fetch&nbsp;Origin".<ol>
					<li>Press the button to "Fetch Origin", which will download the updated environment files.&nbsp;
					</li>
					<li>You may need to press it again if it changes to "Pull&nbsp;Origin"</li>
				</ol>
			</li>
			<li>If you've updated the repo successfully there should be no remaining #'s or arrows on the top right
				corner.<ol>
					<li>If so, click on the Repository menu &gt; Open in&nbsp;Terminal (or Open in GitBash).</li>
				</ol>
			</li>
		</ol>
	</li>
</ol>
<p><br></p>
<h2>Step 3: (Re)Create Your dojo-env using the updated repo</h2>
<ol>
	<li>Run the same commands from the original step "2. Setting Up Your&nbsp;<code>dojo-env</code>&nbsp;Environment"
		(summarized below).<ol>
			<li>If you are unsure about which version of the summary instructions below to use, please go to the
				original Step 2 lesson for your specific OS and follow those steps again.&nbsp;</li>
		</ol>
	</li>
	<li><strong>"Step 2: Setting Up&nbsp;Your Dojo-Env" Summary:</strong>
		<ol>
			<li>Depending on your OS and processor, you will use a different environment file in the conda env create
				command.&nbsp;<ol>
					<li>In the table below find the environment yml file name that is correct for your computer/OS.</li>
				</ol>
			</li>
		</ol>
	</li>
</ol>
<p>Note: Whenever the instructions below refer to your &lt;ENV_FILE&gt; below, it means the filename from the following
	list (without &lt; &gt;).</p>
<table>
	<tbody>
		<tr>
			<td><strong>Computer/OS Type</strong></td>
			<td><strong>Environment File&nbsp;Name</strong></td>
		</tr>
		<tr>
			<td>Windows&nbsp;</td>
			<td>environment_windows.yml</td>
		</tr>
		<tr>
			<td>MacOS with an Intel&nbsp;Processor</td>
			<td>environment_mac_intel.yml</td>
		</tr>
		<tr>
			<td>MacOS with an Apple Chip (m1, m1pro, m2,etc)</td>
			<td>environment_mac_mchip.yml</td>
		</tr>
	</tbody>
</table>
<ul>
	<li>Make sure you are still using a terminal inside the folder for the dojo-env-setup (pwd)</li>
	<li>Run the following command (replace &lt;ENV_FILE&gt; with your filename from the table above)</li>
</ul>
<pre class="rainbow" data-language="ruby">conda env create -f &lt;env_file&gt;</pre>
<ul>
	<li><strong>Wait (patiently) for the dojo-env to be created.&nbsp;</strong>
		<ul>
			<li>Note: the new environment includes many additional tools and can take anywhere from 3-20 minutes to
				finish downloading and installing the packages for the new environment.</li>
		</ul>
	</li>
	<li>Once its complete, run the following "conda activate dojo-env" command:</li>
</ul>
<pre class="rainbow" data-language="ruby">conda activate dojo-env</pre>
<ul>
	<li>Note for windows users:<ul>
			<li>&nbsp;if you see a message that says "your terminal is not set up for conda activate", change the
				command to "source activate"</li>
		</ul>
	</li>
</ul>
<pre class="rainbow" data-language="ruby">source activate dojo-env</pre>
<ul>
	<li>You should now see "(dojo-env)" next to your prompt in your terminal (may be above the prompt, on the left, or
		on the right depending on your OS)</li>
</ul>
<p></p>
<ul>
	<li>After confirming you now see (dojo-env) displayed next to your prompt:<ul>
			<li>Run the following command to make sure Jupyter Notebook/Lab knows your new environment.</li>
		</ul>
	</li>
</ul>
<pre class="rainbow" data-language="ruby">python -m ipykernel install --user --name dojo-env --display-name "Python (dojo-env)"
</pre>
<h2></h2>
<h2>Testing Your New Environment</h2>
<ul>
	<li>From the same terminal window, <strong>start jupyter notebook</strong>
		(run&nbsp;<code>jupyter notebook</code>&nbsp;in your terminal)&nbsp;</li>
	<li><strong>Open the test notebook for your OS (windows vs mac).</strong>
		<ul>
			<li>&nbsp;EnvironmentTester-Mac.ipynb&nbsp; or EnvironmentTester-Windows.ipynb&nbsp;</li>
		</ul>
	</li>
	<li><strong>Select the Kernel Menu &gt; Restart and Run All.&nbsp;</strong>
		<ul>
			<li>The notebook should run all the way to the end.<ul>
					<li>&nbsp;If it doesn't, contact your instructor for assistance.</li>
				</ul>
			</li>
		</ul>
	</li>
</ul>
<h2>Bonus: Jupyter Lab</h2>
<p>Your new dojo-env also includes jupyter lab. It is very similar to jupyter notebook, but has a more fleshed out user
	interface that is more similar to Colab than jupyter notebook.</p>
<p>To start jupyter lab run the following command:</p>
<pre class="rainbow" data-language="ruby">jupyter lab</pre>
<h1></h1>
<h1>Cheat Sheet/Summary Steps</h1>
<p>1. Clone repo or Fetch &amp; Pull:&nbsp;<a
		href="https://github.com/coding-dojo-data-science/dojo-env-setup">https://github.com/coding-dojo-data-science/dojo-env-setup<br></a>
</p>
<p>2. Open in Terminal/GitBash.</p>
<p>Execute the following commands:</p>
<pre class="rainbow" data-language="ruby">## 1. Deactivate dojo-env 
conda activate base
# Windows users may need to use "source activate base"
## 2. Remove dojo-env
conda remove --name dojo-env --all
# press y to confirm
## 3. Create new environment
# run ONE of the following (depending on you computer)
conda env create -f environment_mac_mchip.yml
conda env create -f environment_mac_intel.yml
conda env create -f environment_windows.yml
## Wait patiently, once completed, activate new env
conda activate dojo-env
# windows users may need "source activate dojo-env"
## Add dojo-env kernel to jupyter 
python -m ipykernel install --user --name dojo-env --display-name "Python (dojo-env)"
## Boot up jupyter notebook 
jupyter notebook 
# OR If you previously follwed  "3. Setting dojo-env as your default"
jnb
## Read Final step below code cell
</pre>
<ul>
	<li><strong>Final step:&nbsp;</strong>Open and run the appropriate environment testing notebook for your OS:<ul>
			<li>"EnvironmentTester-mac.ipynb"</li>
			<li>"EnvironmentTester-windows.ipynb"</li>
		</ul>
	</li>
	<li>Notify a TA or instructor if the notebook does not successfully run ALL cells.</li>
</ul>
<h2>Enjoy your new dojo-env!</h2>
<h1><a href="https://github.com/coding-dojo-data-science/dojo-env-setup/tree/testing#new-installations"
		id="user-content-new-installations" class="anchor" aria-hidden="true"></a>
	<p><a href="https://github.com/coding-dojo-data-science/dojo-env-setup/tree/testing#new-installations"
			id="user-content-new-installations" class="anchor" aria-hidden="true"></a></p>
</h1>
<p></p>
<p> <br> </p><br></body></html>