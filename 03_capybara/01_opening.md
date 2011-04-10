!SLIDE purple

# Capybara

!SLIDE

## Simulates user behaviour

!SLIDE

    @@@ruby
    visit('/')
    fill_in('Email', :with => 'capybara@elabs.se')
    fill_in('Password', :with => 'wasserschwein')
    click_button('Sign in')
    page.should have_content('Signed in')

!SLIDE

## Switch seamlessly
## between drivers

!SLIDE

<table>
  <thead>
    <tr>
      <th>Driver</th>
      <th>Good</th>
      <th>Bad</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>rack-test</th>
      <td>Fast, simple</td>
      <td>No javascript</td>
    </tr>
    <tr>
      <th>Selenium</th>
      <td>Real browser<br/>JS &amp; CSS</td>
      <td>Slow<br/>Requires GUI</td>
    </tr>
    <tr>
      <th>Akephalos</th>
      <td>Headless<br/>Good JS support</td>
      <td>Pretty slow</td>
    </tr>
    <tr>
      <th>capybara-envjs</th>
      <td>Fast, Headless</td>
      <td>Bad JS support</td>
    </tr>
  </tbody>
</table>

!SLIDE code

    @@@ruby
    Capybara.current_driver = :selenium

!SLIDE

    @@@cucumber
    @selenium
    Scenario: now uses Selenium

!SLIDE capy3
