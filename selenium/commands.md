
#IMPORTS

from selenium.webdriver import Chrome				//Imports chrome webdriver
driver = Chrome()




# Methods commands

driver.get("<url>")
driver.back() or .forward()
driver.close()							//Close window/tab
driver.quit()



# Output to String
driver.current_url
driver.title
driver.current_window_handle					//Gets windows handle ID



# Windows Size - Management
driver.maximize_window()
driver.fullscreen_window()

driver.get_window_size().get("<width or height>")
driver.set_window_size(<width, height>)

driver.get_window_position().get('<x or y>')
driver.set_window_position(<x, y>)

# Wait Function
from selenium.webdriver.common.by import By
from selenium.webdriver.support import expected_conditions as EC

wait = WebDriverWait(driver, <milliseconds>)
result = wait.until(EC.[condtion](By.<ID or CSS_SELECTOR>) , "<string>")

	[condition]: presence_of_elements_located / visibility_of_element_located / text_to_be_present_in_element


#SWITCHING TABS/WINDOWS
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions

driver.switch_to.window(<window_handle>)


# Using Keystrokes (Keyboard)
from selenium.webdriver.common.keys import Keys

--send Keys:--
element.send_keys("<string>")

element.send_keys(Keys.ENTER) 				//Press Enter on element. Can be concatenated with +
		  Keys.CONTROL / SHIFT / ALT

--key Up/Down:--
webdriver.ActionChains(driver).key_down("<string>")	//Optional parameters: [.send_keys("<string>").perform()]
			      [.key_up]





# ______________________________ HTML ELEMENTS ______________________________
element -> driver.[method]

driver.find_element_by_id("ID")
driver.find_element_by_name("<name>")
driver.find_element_by_tag_name("<string>")


driver.find_element_by_css_selector("<css selectors .class #id; eg. input[type=submit]>")	// Uses CSS selectors to find Element (List/Collection)

driver.text			//Get's HTML content text

element.click()

element.get_attribute("<string>")



#Python

with webdriver as driver:
	driver starts execution
	...
driver quits after indent
