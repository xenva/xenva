- š Hi, Iām @xenva
- š Iām interested in ...
- š± Iām currently learning ...
- šļø Iām looking to collaborate on ...
- š« How to reach me ...

<!---
xenva/xenva is a āØ special āØ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
# print the git branch name if in a git project
parse_git_branch() {
  git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)//'
}
# set the input prompt symbol
ARROW="āÆ"
# define text formatting
PROMPT_BOLD="$(tput bold)"
PROMPT_UNDERLINE="$(tput smul)"
PROMPT_FG_GREEN="$(tput setaf 2)"
PROMPT_FG_CYAN="$(tput setaf 6)"
PROMPT_FG_YELLOW="$(tput setaf 3)"
PROMPT_FG_MAGENTA="$(tput setaf 5)"
PROMPT_RESET="$(tput sgr0)"
# save each section prompt section in variable
PROMPT_SECTION_SHELL="\[$PROMPT_BOLD$PROMPT_FG_GREEN\]\s\[$PROMPT_RESET\]"
PROMPT_SECTION_DIRECTORY="\[$PROMPT_UNDERLINE$PROMPT_FG_CYAN\]\W\[$PROMPT_RESET\]"
PROMPT_SECTION_GIT_BRANCH="\[$PROMPT_FG_YELLOW\]\`parse_git_branch\`\[$PROMPT_RESET\]"
PROMPT_SECTION_ARROW="\[$PROMPT_FG_MAGENTA\]$ARROW\[$PROMPT_RESET\]"
# set the prompt string using each section variable
PS1="
š $PROMPT_SECTION_SHELL āļø  $PROMPT_SECTION_DIRECTORY š $PROMPT_SECTION_GIT_BRANCH š
$PROMPT_SECTION_ARROW "
