Add threshold loadmore with 20% percent height

## Sample usage
```javascript
import { StyleSheet, View, Text, SafeAreaView } from 'react-native'

import ScrollableTabView from 'react-native-scrollable-tab-view'
import TabBar from 'react-native-underline-tabbar'

import LabelView from '../components/label-view'
import MockFlatList from '../components/mock-flatlist'
import MockColorfulList from '../components/mock-colorful-list'

interface State {
  readonly scrollEnabled: boolean
}

export default class ScrollableTabViewScreen extends React.Component<
  {},
  State
> {
  readonly state: State = {
    scrollEnabled: true,
  }
  render() {
    const header = (
      <View
        style={{
          alignSelf: 'stretch',
          height: 200,
          justifyContent: 'center',
          alignItems: 'center',
        }}
      >
        <Text>Header</Text>
      </View>
    )

    return (
      <SafeAreaView style={styles.container}>
        <ScrollableTabView
          collapsableBar={header}
          showsVerticalScrollIndicator={false}
          scrollEnabled={this.state.scrollEnabled}
          renderTabBar={() => (
            <TabBar
              tabBarStyle={{ marginTop: 0 }}
              scrollContainerStyle={{ backgroundColor: '#fff' }}
            />
          )}
        >
          <LabelView tabLabel={{ label: 'First Screen' }}>
            <MockFlatList />
          </LabelView>
          <LabelView tabLabel={{ label: 'Second Screen' }}>
            <MockColorfulList />
          </LabelView>
          <LabelView tabLabel={{ label: 'Third Screen' }}>
            <MockFlatList />
          </LabelView>
          <LabelView tabLabel={{ label: 'Fourth Screen' }}>
            <MockColorfulList />
          </LabelView>
          <LabelView tabLabel={{ label: 'Fifth Screen' }}>
            <MockFlatList />
          </LabelView>
          <LabelView tabLabel={{ label: 'Sixth Screen' }}>
            <MockColorfulList />
          </LabelView>
        </ScrollableTabView>
      </SafeAreaView>
    )
  }
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
  },
})
---

**MIT Licensed**
